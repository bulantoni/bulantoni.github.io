# Начало

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

## Особенности, изучаемого языка:

* Нестрогая типизация - переменная не объявляется с каким-то типом и она может принимать значения разных видов.

* Прототипно-ориентированный - изначально он не был сделан "классическим языком".

* Изначально в нем не было задумано значение о классах, от которых создаются объекты. Вместо этого объекты наследуют черты от других объектов.

* Сценарный - он не компилирует какой-то файл, а является сценарием выполнения.

* Язык браузеров, что говорит о его кросплатформенности.

---
[◁](SUMMARY.md "Оглавление") 📓 [▷](chapter1/chapter1.md "Глава 1")
