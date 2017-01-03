# Глава 1



## Писать на Javascript, просто!

```js
//Создаем переменные и присваиваем им значения
var price = 28.99;
var discount = 10;
//Вычислить цену со скидкой и присвоить переменной total
var total = price - (price * (discount / 100));
//Сравнить переменную total и 25. Если переменная больше...
if (total > 25) {
    freeShipping(); //...выполнить фрагмент freeShipping
}
//Создать переменную count и присвоить ей значение 10.
var count = 10;
//Пока значение count остается больше 0...
while (count > 0) {
    juggle(); //...что-то сделать, а потом...
    count = count - 1 //...уменьшать count на 1
}

//Создать переменную dog с атрибутами name и weight.
var dog = { name: "Rover", weight: 35 };

//Если атрибут weight больше 30...
if (dog.weight > 30) {
    alert("WOOF WOOF"); //...вывести на веб-странице сообщение “WOOF WOOF»
} else {                //В противном случае...
    alert("woof woof"); //...вывести на веб-странице сообщение «woof woof»
}

//Создать переменную circleRadius и присвоить ей значе-
ние 20.
var circleRadius = 20;
//Создать переменную с именем circleArea...
var circleArena =
    Math.PI * (circleRadius * circleArena); //..и присвоить ей результат выражения
(1256.6370614359173)
```

---

## Как создаются команды

При создании контента **HTML** вы обычно размечаете текст, определяя его структуру;
для этого в текст добавляются элементы, атрибуты и значения:

```html
<h1 class="drink">Mocha Caffe Latte</h1>
<p>Espresso, steamed milk and chocolate syrup,
just the way you like it.</p>
```

С **CSS** дело обстоит немного иначе. Разработчик пишет набор правил; каждое
правило выбирает элементы страницы, а затем задает для этих элементов набор
стилей:

```css
/*Для CSS пишутся правила c селекторами 
(например h1.drink и p), определяющими,
к каким частям разметки HTML 
применяется данный стиль.*/

h1.drink {
    color: brown;
}
p {
    font-family: sans-serif;
}
```

Код **JavaScript** состоит из команд. Каждая команда описывает небольшую часть
выполняемой операции, а весь набор команд определяет поведение страницы:

```js
//Набор команд
                                    /*Каждая команда выполняет небольшую
                                    часть работы, например объявляет переменные,
                                    в которых будут храниться используемые значения.*/
var age = 25;
var name = "Owen";
                                    /*Значение переменной может использоваться для 
                                    принятия решений. Возраст пользователя больше 14?*/
if (age > 14) {
    alert("Sorry this page is for kids only!"); 
                                    /*сли больше — сообщаем, 
                                    что пользователь слишком
                                    стар для этой страницы.*/
} else {                            
    alert("Welcome " + name + "!"); 
}                                      
                                    /*А если нет — приветствуем
                                    пользователя по имени (впрочем,
                                    в нашем примере Оуэну 25 лет,
                                    так что сообщение не выводится).*/

```

---

## Переменные и значения

Переменная состоит из имени и выделенной области памяти, которая ему соответствует.

```js
var message;

//После объявления, можно записать в переменную данные (значения)
message = 'Hello';

//Эти данные будут сохранены в соответствующей области 
//памяти и в дальнейшем доступны при обращении по имени:
alert( message );

//Для краткости:
var message = 'Hello!';

//Можно даже объявить несколько переменных сразу:
var user = 'John', age = 25, message = 'Hello';
```

---

## Зарезервированные имена

  Перечень имен, являющихся ключевыми словами языка JavaScript.

  _          |_             |_         |_        |
  -----------|:------------:|:--------:|--------:|
  [break]    | [finally]    | [this]   |class    |
  [case]     | [for]        | [throw]  |enum     |
  [catch]    | [function]   | [try]    |[export] |
  [continue] | [if]         | [typeof] |extends  |
  [debugger] | [in]         | [var]    |[import] |
  [default]  | [instanceof] | [void]   |super    |
  [delete]   | [new]        | [while]  |         |
  [do]       | [return]     | [with]   |         |
  [else]     | [switch]     |          |         |
             |              |          |         |

  **Данные слова не могут употребляться в качестве идентификаторов!*

[break]:(https://developer.mozilla.org/ru/docs/JavaScript/Reference/Statements/break)
[case]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Statements/switch  [catch]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Statements/try...catch
[continue]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Statements/continue
  [debugger]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Statements/debugger
  [default]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Statements/switch
  [delete]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Operators/delete
  [do]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Statements/do...while
  [else]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Statements/if...else
  [finally]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Statements/try...catch
  [for]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Statements/for
  [function]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Statements/function
  [if]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Statements/if...else
  [in]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Statements/for...in
  [instanceof]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Operators/instanceof
  [new]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Operators/new
  [return]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Statements/return
  [switch]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Statements/switch
  [this]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Operators/this
  [throw]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Statements/throw
  [try]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Statements/try...catch
  [typeof]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Operators/typeof
  [var]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Statements/var
  [void]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Operators/void
  [while]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Statements/while
  [with]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Statements/with
  [export]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Statements/export
  [import]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Statements/import

---
































