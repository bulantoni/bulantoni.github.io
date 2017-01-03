# Числа

## Особенности

* Выражаются только в формате `float64` \(8 байт с плавающей точкой\).

* 0.1+0.2 == 0.3; // false

* 1 == 1.0

---

### Ошибочные числа

```javascript
1/0 = Infinity

-1/0 = -Infinity

NaN = не числовое значение
```

1. Любая операция с NaN дает NaN
2. NaN != NaN
3. isNaN\(...\)

---

### Некоторые удобные функции

```javascript
Number(10);                    //   10
Number(“42.23”);              // 42.23
Number(“71oshi”);            //    NaN

parseInt(“18”);                  // 18
parseInt(“19kdjas”);            //  19
parseInt(“74.54”);             //   74
parseFloat(“74.54”);          // 74.54
```

#### `parseInt(num, base)`

```javascript
parseInt("ff");                  //NaN
parseInt("ff","16");            // 255
parseInt(“0x10”);              //   16
parseInt(“0x10”,”10”);        //     0
```

#### `parseFloat(num)`

---

### Преобразования

#### `toExponential`

```javascript
var x = 123456789;     //    undefined
x.toExponential();    //'1.23456789e+8'
x.toExponential(1);          //'1.2e+8'
x.toExponential(2);         //'1.23e+8'
x.toExponential(3);        //'1.235e+8'
```

#### `toFixed`

```javascript
var y = 43.81327;
y.toFixed();                    // '44'
y.toFixed(1);                  //'43.8'
y.toFixed(2);                 //'43.81'
y.toFixed(3);                //'43.813'
```

---

### Битовые операции

```javascript
var n = 7432;

n.toString();          //        '7432'
n.toString(2);        //'1110100001000'
```

_JavaScript_ берет целую часть числа и конвертирует  
в необходимое количество битов, например:

* 0 – два бита \(знак + 0\)
* 1 – два бита
* 2 – три бита



