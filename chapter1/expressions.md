# Выражения

_Выражение_ - единица кода, которая вычисляется в значение

```js
// Арифметические
const x1 = 10;
const x2 = 3 + 5;
const x3 = 3 * 4 + (7 % 2);
const x4 = 3 * 4 + (7 % 2) - sqrt(3);

// Принимающие на вход функцию с каким значением
const x1 = functionName();
const x2 = functionName(3 + 4);
const x3 = functionName(anotherFunction());
const x4 = functionName(anotherFunction() + 4 * 3);
```

_Выражением_ является любой корректный блок кода, который возвращает значение.

В концепции, существует два типа выражений:

1. Присваивающие переменной значение.
2. Вычисляющие выражение без его присваивания.

Выражения в JS делятся на категории:

*

## Порядок вычисления
---

Пример:

```js
// Функция square это квадрат
// sqrt это корень
square(square(sqrt(3 * square(2) + (6 + 7))));

square(square(sqrt(3 * 4 + (6 + 7))))
square(square(sqrt(3 * 4 + 13)))
square(square(sqrt(12 + 13)))
square(square(sqrt(25)))
square(square(5))
square(25)
625
```