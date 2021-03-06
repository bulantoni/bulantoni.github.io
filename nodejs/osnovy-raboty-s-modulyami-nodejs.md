# Основы работы с модулями в Node.js

Любой проект посложнее «Hello World» состоит из некоторого количества файлов, по которым разносят код. Это дает возможность структурировать проект, вынести независимые части, которые можно будет использовать в других проектах и вообще сделать код нагляднее.

Так вот, в Node.js каждый такой файл и представляет собой модуль, который можно подключить.
Подключение происходит с помощью вызова функции require, которой нужно передать путь к файлу.

```js
    var http = require('http');
    var cluster = reqiure('cluster');
```
Нужно отметить, что встроенные модули имеют приоритет над всеми остальными, если в функцию require передано их название. Так к примеру, require('http') всегда вернет встроенный модуль, даже если будет сторонний модуль с таким названием или файл с таким именем. Список всех встроенных модулей и документацию по ним можно найти на [сайте](http://nodejs.org/api/). Исходники этих модулей можно посмотреть в [репозитории проекта](https://github.com/joyent/node/tree/master/lib).

Если передано название модуля и он не является встроенным, тогда идет подключение модуля из папки node_modules. В данной папке находятся все модули, которые добавлены с помощью NPM. NPM — это менеджер пакетов для Node.js, который упрощает поиск и подключение сторонних модулей. На момент написания этой статьи в нем находилось уже 89 503 модулей.

Чтобы подключить модуль который находится в node_modules достаточно указать его название.

```js
    var express = require('express');
    var async = require('async');
```

Когда такой код был вызван из папки '/var/www/demo', тогда Node.js попытается найти указанные модули в следующих папках:

    /var/www/demo/node_modules
    /var/www/node_modules
    /var/node_modules
    /node_modules

Node.js рекурсивно, каждый раз переходя в родительскую папку, будет искать папку node_modules с нужным модулем. NPM также даем возможность установить модуль глобально (`npm install -g MODULE`), тогда он будет доступен из любого места.

Еще один вариант подключения, если переданный параметр в функцию require начинается с /, ../, или ./, тогда файл для подключения будет происходить по абсолютному пути или относительно текущей папки.

```js
    var logger = require('../lib/logger');
    var profiler = require('/var/lib/profiler');
```
Сначала будет проверено или существует файл с именем точно соответствующим указанному, если такой файл не будет найден, тогда Node.js попытается подключить файл добавляя к имени разные расширения: .js, .json, а также .node.

Поэтому нет необходимости указывать файл с расширением, так как require('./lib/users.js') и require('./lib/users') подключит один и тот же модуль.

Модули могут быть настолько большими, что может возникнет необходимость вынести некоторые части в отдельные файлы, чтобы лучше организовать код модуля. А так как эти файлы используются только этим модулем, не нужно чтобы они находились среди остальных модулей. Для решения этой проблемы в Node.js есть возможность организовать модуль в виде папки в которой будут находится все файлы модуля. Чтобы подключить такой модуль нужно просто передать путь данной папки в функцию require.

Представим, что у нас есть модули и один и них logger представлен в виде папки с файлами:

    ┌─auth.js
    ├─user.js
    └─logger
        ├─ index.js
        ├─ console.js
        ├─ package.json
        ├─ config.js
        └─ db.js

Подключение модуля logger заключается в том, что мы просто передадим путь к этой папки:

```js
    var require('./logger');
```

Дальше Node.js сам попытается определить какой из файлов папки представляет собой точку входа для модуля. Для начала будет проверено или существует в папке файл package.json в котором будет указано в поле main имя файла, который нужно подключить.

```js
    {
        main: "./console.js"
    }
```

Будет загружен файл './logger/console.js'. Если файла package.json нету, тогда Node.js попытается подключить файлы './logger/index.js' или './logger/index.node'.

С подключением модулей закончили, теперь рассмотрим несколько интересных моментов, связанных с ними. Независимо от того как вы подключаете модуль, он кэшируется сразу после подключения. Это означает, что сколько бы раз не подключался модуль, его код исполнится только один раз.

Это поведение можно изменить, если после каждого вызова модуля удалять его из кэша.

```js
    delete require.cache[ module ];
```

_module_ — это параметр, который вы передавали функции require для подключения модуля.

Так что если вам нужно, чтобы ваш модуль каждый раз когда его подключают что-то выполнял — для этого нужно или чистить кэш, или возвращать функцию, которую нужно будет вызвать, что выполнить работу.

Чтобы получить полный путь, по которому был найден модуль, можно воспользоваться функцией require.resolve.

```js
    var modulePath = require.resolve('express');
```

Так как вы не знаете где находится папка node_modules с нужным модулем, можно воспользоваться тем, что Node.js сам пройдется по всем возможным местам расположения модуля.

Функция require кроме всего этого имеет еще одно полезное свойство main. Оно хранит в себе модуль который был запущен из командной строки. Так что из любого модуля можно узнать или данный модуль был запущен напрямую или он был подключен как зависимость другого модуля.

Кроме уже рассмотренной функции require, в каждом модуле доступен объект module. Основная задача этого объекта дать возможность модулю вернуть результат своего исполнения. Это может быть и объект, и функция, и строка — любой тип данных.

В объекта module есть свойство exports и ему нужно присваивать все что вы хотите вернуть из модуля. Именно module.exports вернется как результат подключения модуля.

```js
    module.exports.createUser = function () {
      return new User();
    }
```

После подключения модуля с данным кодом, в ответе будет объект с данным методом.

Можно также воспользоваться более кратким вариантом, переменной exports, которая по-сути просто ссылка на module.exports.

```js
    exports.createUser = function () {
      return new User();
    }
```

Так как это ссылка, между этими двумя вариантами существует одна важная разница. Результат работы модуля можно вернуть только через объект module.exports, поэтому, если переменной exports присвоить другое значение, она уже не будет ссылаться на module.exports, а значит модуль ничего и не вернет.

А вот сам module.exports можно изменить. Вместо объекта, например, можно вернуть функцию и тогда результатом работы модуля будет не объект с методом в виде некоторой функции, а сама функция.

С помощью module также можно узнать или данный модуль запущен из командной строки. Для этого нужно проверить свойство module.parent — оно должно быть undefined.

Я думаю этой информации будет достаточно для работы с модулями в Node.js. Также я рекомендую ознакомится с [NPM](https://www.npmjs.org/), так как с ним вам придется сталкиваться в каждом проекте на Node.js.