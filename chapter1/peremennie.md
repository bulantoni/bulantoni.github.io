# Переменные

## Именование

*Переменные* состоят из имени и выделенной области памяти.

На имя переменной в JavaScript наложены всего два ограничения.

1. Имя может состоять из: букв, цифр, символов $ и _
2. Первый символ не должен быть цифрой.

`$` и `_` являются такими же обычными символами, как буквы.

```js
var $ = 1; // объявили переменную с именем '$'
var _ = 2; // переменная с именем '_'

alert( $ + _ ); // 3
```

## Зарезервированные имена

  Перечень имен, являющихся ключевыми словами языка JavaScript.

  .          |.             |.         |.        |
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

  **Данные слова не могут употребляться в качестве идентификаторов!*

[break]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Statements/break
[case]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Statements/switch
[catch]:https://developer.mozilla.org/ru/docs/JavaScript/Reference/Statements/try...catch
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
