<div align="center">

# Глава 5: Условные инструкции и циклы

</div>

<br />

<div align="center">

## Цель главы

</div>

Цель главы:
- познакомиться с условными инструкциями;
- изучить приведение типов к логическому типу;
- рассмотреть встроенные в JS циклы.



<br />

<div align="center">

## Условные инструкции

</div>

**Условные инструкции** - это конструкции языка, которые позволяют выполнять определенный блок кода только при выполнении определенного условия.

В JS условные инструкции представлены ключевыми словами `if`, `else if`, `else`, `switch` и тернарным оператором.



<br />

<div align="center">

### Инструкция `if`

</div>

**Инструкция `if`** — выполняет блок кода только в том случае, если заданное условие истинно. Условие задается выражением в круглых скобках.

```js
if (true) {
  console.log('Этот код будет выведен в консоль, так как условие true');
}

if (false) {
  console.log('Этот код НЕ будет выведен в консоль, так как условие false');
}
```

<br />

Так как условие — это выражение, значит мы можем помещать в круглые скобки любой вычисляемый код.

```js
if (10 > 5) {
  console.log('Это сообщение будет выведено в консоль, так как 10 больше чем 5');
}

if (3 < 0) {
  console.log('Это сообщение НЕ будет выведено в консоль, так как 3 не меньше 0');
}
```

```js
const num1 = 100;
const num2 = 100;

if (num1 === num2) {
  console.log('Это сообщение будет выведено в консоль, так как значение num1 равняется значению num2');
}
```



<br />

<div align="center">

### Инструкция `else if`

</div>

Инструкция `else if` позволяет добавить дополнительное условие для проверки.

```js
if (10 > 100) {
  console.log('Этого в консоли не будет');
} else if (100 > 10) {
  console.log('Это сообщение будет выведено в консоль, так как 100 больше 10');
}
```

<br />

Однако следует помнить, что очередь до `else if` дойдет только в том случае, если условие инструкции `if` было ложным.

```js
if (true) {
  console.log('В консоли!');
} else if (true) {
  // До этого участка кода дело не дойдет, так как инструкция if — истинна
  console.log('Не будет выведено никогда...');
}
```

<br />

В ветвление можно добавлять сколько угодно инструкций `else if`.

```js
if (false) {
  console.log('Не будет выведено никогда...');
} else if (false) {
  console.log('Не будет выведено никогда...');
} else if (false) {
  console.log('Не будет выведено никогда...');
} else if (true) {
  console.log('В консоли!');
}
```



<br />

<div align="center">

### Инструкция `else`

</div>

**Инструкция `else`** — выполняет блок кода только в том случае, если все предыдущие условия были ложными.

```js
if (false) {
  console.log('Не будет выведено никогда...');
} else {
  console.log('В консоли! Так как предыдущее условие ложно');
}
```

<br />

Инструкция `else` должна идти самой последней в цепочке ветвлений.

```js
if (false) {
  console.log('Не будет выведено никогда...');
} else if (false) {
  console.log('Не будет выведено никогда...');
} else if (false) {
  console.log('Не будет выведено никогда...');
} else {
  console.log('В консоли! Так как все предыдущие условия ложны');
}
```



<br />

<div align="center">

### Применение условных инструкций

</div>

Условные инструкции позволяют адаптироваться к ситуациям, когда определенный код должен быть запущен только при каком-либо условии.

**Пример** Вывод в консоль статуса пользователя.
```js
const status = 'online';

if (status === 'online') {
  console.log('Пользователь онлайн');
} else {
  console.log('Пользователь оффлайн');
}
```

<br />

**Пример** Ограничение доступа к сайту пользователям младше 18-ти лет.
```js
const age = 17;

if (age >= 18) {
  console.log('Вход на сайт разрешен');
} else {
  console.log('Вам еще нет 18! Доступ к сайту отказан.');
}
```

<br />

```js
const role = 'admin';

if (role === 'admin') {
  console.log('Доступ к сайту: полный');
} else if (role === 'moderator') {
  console.log('Доступ к сайту: чтение и редактирование');
} else {
  console.log('Доступ к сайту: только чтение');
}
```



<br />

<div align="center">

### Приведение к логическому типу

</div>

Выражение в условии после вычисления **всегда** будет преобразовываться к логическому типу, потому что условие в результате ожидает либо `true`, либо `false`.

Все приведенные ниже значения будут преобразованы в `false`:
- `false`;
- `''` - пустая строка;
- `0` - из чисел только 0;
- `NaN`;
- `null`;
- `undefined`.

Все остальные возможные значения будут конвертироваться в `true`:
- `true`;
- `Павел` - любая не пустая строка;
- `1` - любое число отличное от 0;
- `{}` - пустой или заполненный объект;
- `[]` - пустой или заполненный массив;
- `function () {}` - любая функция;
- `Symbol()` - любой символ.





<br />

<div align="center">

### Инструкция `switch`

</div>

**Инструкция `switch`** — вызывает выражение и сравнивает его результат с несколькими вариантами. В случае, если один из вариантов совпадает с результатом выражения, то выполняется соответствующий блок кода. Если ни один из вариантов не совпадает с результатом выражения, то выполняется отдельно заданный блок кода по-умолчанию.

```js
const country = 'Россия';

switch (country) {
  case 'Казахстан':
    console.log('Этот блок кода не будет запущен');
    break;
  case 'Россия':
    console.log('В консоли! Так как country равен значению Россия');
    break;
  case 'Туркменистан':
    console.log('Этот блок кода не будет запущен');
    break;
}
```

<br />

В случае, если ни один из вариантов не подходит, то будет выполняться блок кода `default`.

```js
const dayTime = 'Утро';

switch (dayTime) {
  case 'День':
    console.log('...');
    break;
  case 'Вечер':
    console.log('...');
    break;
  case 'Ночь':
    console.log('...');
    break;
  default:
    console.log('В консоли! Потому что значение dayTime не подходит ни под один из предыдущих вариантов')
}
```

<br />

Ключевое слово `break` — прерывает выполнение следующих за ним блоков кода. Если не проставлять `break`, то будут выполняться все следующие блоки кода до тех пор, пока не будет встречен первый `break`.

```js
const name = 'Павел';

switch (name) {
  case 'Артем':
    console.log('...');
  case 'Павел':
    console.log('Привет, Павел!');
  case 'Илон':
    console.log('Привет, Илон!');
}
// При таком коде консоль будет приветствовать и Павла и Илона
```

<br />

Однако, отсутствие `break` полезно в ситуациях, когда под один блок кода подходит сразу несколько вариантов.

В примере ниже, сразу для нескольких вариантов ролей выполняется один и тот же код.

```js
const role = 'moderator';

switch (role) {
  case 'admin':
    console.log('...');
    break;
  case 'moderator':
  case 'newsmaker':
  case 'contentmaker':
    console.log('В консоли!');
    break;
}
```



<br />

<div align="center">

### Тернарный оператор

</div>

**Тернарный оператор** — это сокращенный способ записи условной инструкции `if else`.

Синтаксис тернарного оператора следующий: `условие ? выражение1 : выражение2`.

Где:
- `условие` — выражение, которое в результате будет приведено либо к `true`, либо к `false`;
- `выражение1` — выражение, которое будет запущено только если условие истинно;
- `выражение2` — выражение, которое будет запущено только если условие ложно.

```js
10 > 5 ? console.log('Да!') : console.log('Нет!')
// Да!
```

```js
const age = 17;

age >= 18 ? console.log('Да!') : console.log('Нет!');
// Нет!
```

<br />

Результат работы тернарного оператора может быть записан в переменную или возвращен из функции.

```js
const number = 10;

const result = number % 2 === 0 ? 'Четное число' : 'Нечетное число';
console.log(result);
// Четное число
```





<br />

<div align="center">

## Циклы

</div>

**Цикл** — это запуск одного и того же кода несколько раз.



<br />

<div align="center">

### Цикл `while`

</div>

**Цикл `while`** — выполняет код до тех пор, пока указанное условие истинно.

```js
let i = 0;

while (i < 3) {
  console.log(i);
  i++;
}
// 0
// 1
// 2
```



<br />

<div align="center">

### Цикл `for`

</div>

**Цикл `for`** — выполняет код до тех пор, пока указанное условие истинно.

```js
for (let i = 0; i < 3; i++) {
  console.log(i);
}
// 0
// 1
// 2
```



<br />

<div align="center">

### Остановка цикла `break`

</div>

**Ключевое слово `break`** — прерывает выполнение цикла.

**Пример.** Прерывание цикла, когда `i` становится равен `3`.
```js
for (let i = 0; i < 10; i++) {
  if (i === 3) {
    break;
  }
  console.log(i);
}
// 0
// 1
// 2
```



<br />

<div align="center">

### Прерывание итерации `continue`

</div>

**Ключевое слово `continue`** — прерывает текущую итерацию цикла и переходит к следующей.

**Пример.** Вывод в консоль только четных чисел.
```js
for (let i = 0; i < 9; i++) {
  if (i % 2) {
    continue;
  }
  console.log(i);
}
// 0
// 2
// 4
// 6
// 8
```



<br />

<div align="center">

### Цикл `for ... of`

</div>

**Цикл `for ... of`** — проходит по всем элементам массива (и другим перечислимым объектам).

```js
const cars = ['Ford', 'Toyota', 'Lexus']

for (let car of cars) {
  console.log(car)
}
// 'Ford'
// 'Toyota'
// 'Lexus'
```



<br />

<div align="center">

### Цикл `for ... in`

</div>

**Цикл `for ... in`** — проходит по всем перечислимым свойствам объекта.

```js
const cars = { model: 'AUDI A8', year: '2019', color: 'brown' }

for (let key in obj) {
  console.log(key + ' = ' + obj[key]);
}
// 'model = AUDI A8'
// 'year = 2019'
// 'color = brown'
```






