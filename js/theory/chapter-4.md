<div align="center">

# Глава 4: Объекты

</div>

<br />

<div align="center">

## Цель главы

</div>

Наша цель на данную главу — полностью разобрать конструкцию объекта:
- что такое объект и для чего он нужен;
- как записывается объект;
- что такое свойства, ключи и значения объекта;
- все возможные виды записи ключей и значений, а также нюансы работы с ними;
- какие операции можно производить с объектом и как это делать.

<br />

<div align="center">

## Что такое объект

</div>

**Объект** — это набор свойств, состоящих из пары `ключ: значение`.

**Пример 1.1.** Объявление объекта.
```js
const name = {
  'ключ1': 'значение 1',
  'ключ2': 'значение 2'
};
```

<br />

Здесь:
- `name` — название объекта, по которому мы можем к нему обращаться;
- `ключ1: значение1` (вся строка целиком) — свойство объекта;
- `ключ2: значение2` (вся строка целиком) — второе свойство объекта;
- `ключ1` и `ключ2` — названия ключей, по которым хранятся значения;
- `значение 1` и `значение 2` — хранимые в объекте значения.



<br />

<div align="center">

## Зачем нужны объекты?

</div>

<br />

<div align="center">

### Единое место хранения взаимосвязанных данных

</div>

Объект — это удобное хранилище нескольких однородных/взаимосвязанных значений.

Если бы не существовало объектов, то для каждого значения нам приходилось бы создавать отдельную переменную. Выглядело бы это как в примере ниже.

**Пример 2.1.** Если бы объектов не существовало.
```js
const userName = 'Павел';
const userAge = 38;
const userCity = 'Санкт-Петербург';
```

<br />

Хранить взаимосвязанные данные в виде отдельных переменных достаточно неудобно:
1. Нам нужно всегда помнить, какие из переменных взаимосвязанны. Помнить об этом в момент написания кода легко, но вернувшись к написанному коду через пару месяцев — можно с легкостью забыть что откуда.
2. Между отдельными переменными можно вставить любой другой код. Тогда может возникнуть ситуация, что взаимосвязанные переменные расположены вдали друг от друга.
3. При перемещении кода в другое место — нужно также искать и переносить все взаимосвязанные переменные.

Если подумать дольше, то можно будет найти еще несколько минусов такого подхода.

<br />

При помощи объектов, мы можем хранить взаимосвязанные данные в одном месте и в более удобном/наглядном виде записи.

**Пример 2.2.** Те же данные, но в объекте.
```js
const user = {
  name: 'Павел',
  age: 38,
  city: 'Санкт-Петербург'
};
```





<br />

<div align="center">

### Описание чего-либо

</div>

В большинстве случаев, объект используется как описание какой-либо сущности (товара, пользователя, страницы, фотографии, настроек и т.д.).

<br />

С помощью объекта можно описать товар в интернет-магазине.

**Изображение 1.1.** Товар в интернет-магазине.

<div align="center">

![Товар в интернет-магазине](/assets/chapter-4/chapter-4.01.jpg)

</div>

**Пример 2.3.** Пример объекта с данными о товаре.
```js
const boardgame = {
  title: 'Сумерки Империи',
  playtime: 360,
  weight: 4.34,
  manufacturer: 'Hobby World'
};
```

<br />
<br />

С помощью объекта можно описать пользователя сайта.

**Изображение 1.2.** Пользователь сайта.

<div align="center">

![Пользователь сайта](/assets/chapter-4/chapter-4.02.jpg)

</div>

**Пример 2.4.** Пример объекта с данными о пользователе.
```js
const user = {
  firstName: 'Павел',
  lastName: 'Дуров',
  city: 'Санкт-Петербург',
  work: 'Telegram',
  backgroundImage: null
};
```

<br />
<br />

С помощью объекта можно описать настройки игры.

**Изображение 1.3.** Настройки игры.

<div align="center">

![Пользователь сайта](/assets/chapter-4/chapter-4.03.jpg)

</div>

**Пример 2.5.** Пример объекта с настройками игры.
```js
const graphicSettings = {
  multithreadedRendering: true,
  materialQuality: 'medium',
  textureQuality: 'high',
  detailQuality: 'high',
  UIQuality: 'high',
  vignette: true,
  vSync: false
};
```

<br />

С помощью объекта можно описать всё!

В дальнейшем, описанные объекты пригодятся нам при создании приложения.





<br />

<div align="center">

### Расширенный функционал

</div>

В JavaScript встроены удобные инструменты для работы с объектами. Мы можем:
- с помощью циклов обращаться ко всем свойствам объекта и что-то с ними делать;
- с помощью наследования расширять функционал объекта;
- запрещать изменение определенных свойств или всего объекта;
- и так далее.

С отдельными переменными труднее делать что-то подобное.





<br />
<br />

<div align="center">

## Ключи

</div>

**Ключ или имя свойства (англ. key, property name)** — это название свойства к которому привязано значение.

С помощью ключа можно:
- добавить значение в объект;
- изменить значение в объекте;
- получить значение из объекта.





<br />

<div align="center">

### Виды записи ключа

</div>

Ключ может быть записан:
- в виде набора символов без кавычек;
- в виде строки;
- в виде числа;
- в виде квадратных скобок с выражением внутри.

```js
const object = {
  firstKey: 'значени 1',
  'secondKey': 'значение 2',
  0: 'значение 3',
  ['thirdKey']: 'значение 4'
};
```

<br />

Но каким образом мы бы ни записывали ключ, по итогу он **ВСЕГДА** будет преобразован в строку движком JavaScript.





<br />

<div align="center">

### Ключ в виде набора символов

</div>

Запись ключа в виде набора символов без кавычек должна быть написана в `верблюжьейНотации` или `змеиной_нотации`.

**Пример.** Запись ключа в виде набора символов без кавычек.
```js
const object = {
  first: 'значение 1',
  secondKey: 'значение 2',
  myThirdKey: 'значение 3',
  fourth_key: 'значение 4'
};
```

<br />

В таком формате записи ставить пробелы и дефисы между символами запрещено.

**Пример.** Ошибка! В записи ключа без кавычек ставить пробелы и дефисы запрещено!
```js
const object = {
  first key: 'значение 1',
  my-second-key: 'значение 2'
};
```

<br />

Набор символов может состоять из букв, чисел и нижнего подчеркивания.

Единственное исключение: название ключа не может начинаться с числа, за которым идут другие символы.

**Пример.** Ошибка! Неверные названия ключей.
```js
const object = {
  10age: 'значение 1',  // число с последующим набором букв запрещено
  {}: 'значение 2'      // фигурные скобки запрещены
};
```





<br />

<div align="center">

### Ключ в виде строки

</div>

Запись ключа в виде строки позволяет использовать любой набор символов, включая пробелы и дефисы.

**Пример.** Запись ключа в виде строки.
```js
const object = {
  'first': 'значение 1',
  'secondKey': 'значение 2',
  'my third key': 'значение 3',
  'fourth-key': 'значение 4'
};
```





<br />

<div align="center">

### Ключ в виде числа

</div>

В качестве названия ключа можно использовать положительные целые числа.

**Пример.** Запись ключа в виде числа.
```js
const object = {
  0: 'значение 1',
  1: 'значение 2',
  50: 'значение 3'
};
```

<br />

Использовать отрицательные числа в названии ключа запрещено.

**Пример.** Ошибка! Использование отрицательных чисел запрещено.
```js
const object = {
  -1: 'значение 1',
  -50: 'значение 2'
};
// SyntaxError: Unexpected token '-'
```

<br />

Использовать дробные числа не рекомендуется. Причина: лишние нули в названии отбрасываются, что может привести к неожиданным результатам.

**Пример.** Дробные числа в названии ключа.
```js
const object = {
  1.23: 'значение 1',
  5.00: 'значение 2'
};

console.log(object);
// У ключа 5.00 были отброшены два нуля.
// {
//   1.23: 'значение 1',
//   5: 'значение2'
// }
```





<br />

<div align="center">

### Ключ в квадратных скобках

</div>

Запись ключа в квадратных скобках позволяет использовать выражения.

**Пример.** Синтаксис ключа в квадратных скобках.
```js
const object = {
  [выражение1]: 'значение 1',
  [выражение2]: 'значение 2',
};
```

<br />

Выражение может понадобиться:
- когда название ключа заранее неизвестно;
- когда название ключа динамически меняется в процессе выполнения кода.

Порядок вычисления названия ключа:
1. Вычисляется выражение в квадратных скобках.
2. Результат выражения преобразуется в строку.

Таким образом, какое выражение ни было бы написано в квадратных скобках — итоговый ключ всегда будет строкой.

**Пример.** Запись ключа в квадратных скобках.
```js
const object = {
  ['ключ']: 'значение 1',
  [10]: 'значение 2'
};

console.log(object);
// {
//   'ключ': 'значение 1'
//   10: 'значение 2'
// }
```

<br />

В примере ниже: при установке названия ключа, JavaScript пойдет в память, и узнает значение константы `key`. Далее значение константы `key` будет записано как название ключа.

**Пример.** Получение названия ключа из переменной.
```js
const key = 'name';

const object = {
  [key]: 'Павел'
};

console.log(object);
// {
//   name: 'Павел'
// }
```

<br />

В следующем примере: при установке названия ключа, JavaScript запустит функцию `getKey()` и будет ждать результата её работы. Далее результат работы `getKey()` будет записан как название ключа.

**Пример.** Получение названия ключа из функции.

```js
function getKey() {
  return 'name';
}

const object = {
  [getKey()]: 'Павел'
};

console.log(object);
// {
//   name: 'Павел'
// }
```

<br />

Как мы знаем из предыдущей главы: если в функции отсутствует оператор `return`, то функция вернет `undefined`.

В следующем примере, мы убрали `return` из тела функции, и ожидаемо получили `undefined` как название ключа.

**Пример.** Получение названия ключа из функции без `return`.

```js
function getKey() {
  'name';
}

const object = {
  [getKey()]: 'Павел'
};

console.log(object);
// {
//   undefined: 'Павел'
// }
```

<br />

**Обратите внимание!** В квадратных скобках функцию нужно обязательно вызвать! Иначе в названии ключа будет получен строковый код функции.

**Пример.** Что будет если функцию не вызвать.
```js
function getKey() {
  return 'name';
}

const object = {
  [getKey]: 'Павел'
};

console.log(object);
// Вместо ожидаемого ключа `name` мы получили код функции целиком
// {
//   'function getKey() {↵ return 'name';↵}': 'Павел'
// }
```

<br />

При попытке преобразовать любой объект в строку, мы получим значение `[object Object]`. При этом неважно какое будет содержание у объекта, результат будет один и тот же.

Поэтому объект в выражении названия ключа использовать не стоит.

**Пример.** Пустой объект в выражении названия ключа.
```js
const object = {
  [{}]: 'Павел'
};

console.log(object);
// {
//   [object Object]: 'Павел'
// }
```

<br />

**Пример.** Заполненный объект в выражении названия ключа.
```js
const object = {
  [{ key: 'name' }]: 'Павел'
};

console.log(object);
// {
//   [object Object]: 'Павел'
// }
```

<br />

Массив преобразовывается в строку путем преобразования каждого элемента массива в строку.

**Пример.** Массив в выражении названия ключа.
```js
const object = {
  [[1, 2, {}]]: 'Павел'
};

console.log(object);
// {
//   1,2,[object Object]: 'Павел'
// }
```





<br />

<div align="center">

### Ключ станет строкой

</div>

Название ключа в JavaScript — это всегда строка. Если в названии ключа мы используем:
- числа или символы без кавычек — они будут преобразованы в строки;
- квадратные скобки — сперва выражение внутри скобок будет вычислено, а затем преобразовано в строку.

**Пример.** Эти два объекта абсолютно идентичны.
```js
const key = 'fourth';

const object1 = {
  first: 'значени 1',
  'second': 'значение 2',
  0: 'значение 3',
  [key]: 'значение 4'
};

const object2 = {
  'first': 'значени 1',
  'second': 'значение 2',
  '0': 'значение 3',
  'fourth': 'значение 4'
};
```


<br />

<div align="center">

### Дублирование ключей

</div>

Названия ключей в объекте должны быть уникальными. Если в объекте несколько ключей имеют одинаковое название, то последний из них заменит все предыдущие.

**Пример.** Объект с дублирующимися ключами.
```js
const object = {
  one: 'значение 1',
  one: 'значение 2',
  one: 'значение 3'
};

// При такой записи в итоге мы получим следующий объект:
// {
//   one: 'значение 3'
// }
```






<br />
<br />

<div align="center">

## Значения свойств

</div>

**Значение свойства (англ. property value)** — это хранимая информация в свойстве.

**Пример.** Синтаксис значения свойства.
```js
const object = {
  key1: выражение1,
  key2: выражение2,
};
```

<br />

Значением в свойстве может быть любой тип данных или любое выражение: числа, строки, логический тип, массивы, функции, переменные, другие объекты и т.д.

**Пример.** Примеры значений в объекте.
```js
const object = {
  number: 100,
  string: 'Строка',
  boolean: true,
  array: [1, 2, 3],
  anotherObject: {
    key: 'value'
  }
};
```

<br />

При этом вложенность объектов друг в друга может быть большой.

**Пример.** Объекты в объекте.
```js
const object = {
  firstObject: {
    secondObject: {
      thirdObject: {
        title: 'Вложенные объекты'
      }
    }
  },
};
```

<br />

В качестве значения могут быть константы и переменные.

В следующем примере: когда JavaScript встретит константу/переменную в значении свойства, он пойдет в память, достанет оттуда значение константы/переменной и запишет результат в значение свойства.

**Пример.** Константы и переменные в качестве значения.
```js
const firstName = 'Павел';
let age = 38;

const object = {
  name: firstName,
  age: age
};

console.log(object);
// {
//   name: 'Павел',
//   age: 38
// }
```

<br />

Если название константы/переменной совпадает с названием ключа в объекте — то название ключа можно не писать.

**Пример.** Сокращенная запись.
```js
const name = 'Павел';
let age = 38;

const object = {
  name,
  age
};

console.log(object);
// {
//   name: 'Павел',
//   age: 38
// }
```

<br />

В качестве значения могут быть функции. Если в значение записываем:
- вызванную функцию — получим в значение результат работы функции;
- функцию без вызова — получим в значение эту функцию (подробнее далее в разделе "Методы").

**Пример.**
```js
function getName() {
  return 'Павел';
}

const object = {
  name1: getName(),
  name2: getName
};

console.log(object);
// {
//   name1: 'Павел',
//   name2: getName()
// }
```




<br />
<br />

<div align="center">

## Операции с объектом

</div>

**Средства доступа к свойствам (англ. Property accessors)** — встроенные инструменты, которые позволяют работать с объектами.

Есть два вида записи средств доступа к свойствам:
- через точку `.`;
- через квадратные скобки `[]`.

**Пример.** Синтаксис двух видов средств доступа к свойствам.
```js
выражение.ключ;
выражение[выражение];
```

[comment]: <> (<br />)

[comment]: <> (Средство доступа через точку:)

[comment]: <> (- выражение перед точкой должно возвращать объект;)

[comment]: <> (- ключ после точки — название ключа в объекте.)

[comment]: <> (```js)

[comment]: <> (const object = {)

[comment]: <> (})

[comment]: <> (```)


<br />

<div align="center">

### Получение значения свойства

</div>

Средства доступа позволяют получить значение свойства по ключу.

**Пример.** Получение значений свойств.
```js
const user = {
  name: 'Павел',
  lastName: 'Дуров',
  user_age: 38,
};

// Через точку
console.log(user.name);      // Павел
console.log(user.lastName);  // Дуров
console.log(user.user_age);  // 38
console.log(user.another);   // undefined, такого свойства в объекте нет

// Через квадратные скобки
console.log(user['name']);      // Павел
console.log(user['lastName']);  // Дуров
console.log(user['user_age']);  // 38
console.log(user['another']);   // undefined, такого свойства в объекте нет
```





<br />

<div align="center">

### Ограничения точки

</div>

Ключ после точки должен быть написан при помощи набора символов без кавычек. Это означает, что:
- нельзя использовать строки;
- нельзя начинать название ключа с числа;
- нельзя получить ключ, в названии которого есть пробелы или дефисы.

**Пример.** Ошибка! Неверное использование средства доступа через точку.
```js
const user = {
  name: 'Павел',
  'last name': 'Дуров',
  10: true
};

console.log(user.'last name');  // Нельзя исопльзовать строки!
console.log(user.last name);  // Нельзя исопльзовать пробелы!
console.log(user.10);  // Нельзя использовать числа!
```





<br />

<div align="center">

### Возможности квадратных скобок

</div>

Возможность использовать выражения в квадратных скобках значительно расширяет наши возможности:
- можно использовать любое название ключа;
- можно использовать константы/переменные;
- можно использовать вызов функции.

Единственное условие: выражение должно в итоге быть преобразовано в корректную строку.

**Пример.** Получение значений свойств через квадратные скобки.
```js
const user = {
  name: 'Павел',
  'last name': 'Дуров',
  10: true
};

console.log(user['name']);       // Павел
console.log(user['last name']);  // Дуров
console.log(user[10]);           // true
console.log(user['another']);    // undefined, такого свойства в объекте нет
```

<br />

В примере ниже: когда JavaScript встречает константу/переменную в квадратных скобках, он обращается к памяти, забирает оттуда значение константы/переменной и подставляет полученное значение в выражение.

**Пример.** Получение значения свойства при помощи переменной в квадратных скобках.
```js
const user = {
  name: 'Павел',
};

const key = 'name';

console.log(user[key]);  // Павел
```

<br />

Если в квадратных скобках находится вызов функции: JavaScript вызовет функцию, подождет возвращаемое значение, и подставит полученный результат в выражение.

**Пример.** Получение значения свойства при помощи вызова функции в квадратных скобках.
```js
const user = {
  name: 'Павел',
};

function getKey() {
  return `name`;
}

console.log(user[getKey()]);  // Павел
```





<br />

<div align="center">

### Отличия квадратных скобок от точки

</div>

Отличия квадратных скобок от точки:
- квадратные скобки позволяют использовать любые названия ключей;
- внутри квадратных скобок можно использовать JavaScript-выражение.

Получается, квадратные скобки имеют явные преимущества перед точкой?  
Да, имеют.

Тогда зачем нужен вариант с точкой?  
Синтаксис с точкой немного короче, легче набирается с клавиатуры и выглядит лаконичнее (что особенно будет заметно при работе со вложенными объектами).





<br />

<div align="center">

### Добавление свойств в объект

</div>

Средства доступа к свойствам позволяют добавить свойство в объект.

**Пример.** Синтаксис добавления свойств в объект.
```js
выражение.ключ = выражение;
выражение[выражение] = выражение;
```

<br />

**Пример.** Добавление свойства в объект через точку.
```js
const object = {};

object.name = 'Павел';
console.log(object);
// {
//   name: 'Павел'
// }

object.age = 38;
console.log(object);
// {
//   name: 'Павел',
//   age: 38
// }
```

<br />

**Пример.** Добавление свойства в объект через квадратные скобки.
```js
const object = {};

object['name'] = 'Павел';
console.log(object);
// {
//   name: 'Павел'
// }

object['age'] = 38;
console.log(object);
// {
//   name: 'Павел',
//   age: 38
// }
```

<br />

**Пример.** Добавление свойства в объект с использованием возможностей выражения.
```js
const object = {};

const key = 'name';
object[key] = 'Павел';

console.log(object);
// {
//   name: 'Павел'
// }


function getKey() {
  return 'age';
}

object[getKey()] = 38
// {
//   name: 'Павел',
//   age: 38
// }
```





<br />

<div align="center">

### Изменение значений в объекте

</div>

Средства доступа к свойствам позволяют изменять значения свойств объекта.

**Пример.** Изменение значения.
```js
const object = {
  name: 'Павел',
  age: 38
};

object.name = 'Артур';
console.log(object);
// {
//   name: 'Артур',
//   age: 38
// }

object['age'] = 40;
console.log(object);
// {
//   name: 'Артур',
//   age: 40
// }
```




<br />

<div align="center">

### Удаление свойств из объекта

</div>

**Оператор `delete`** — позволяет удалять свойства из объекта.

**Пример.** Удаление свойств из объекта.
```js
const object = {
  name: 'John',
  age: 30,
  isMarried: true
};

delete object.isMarried;
console.log(object);
// {
//   name: 'John',
//   age: 30
// }

delete object['age'];
console.log(object);
// {
//   name: 'John',
// }
```





<br />

<div align="center">

### Извлечение значений свойств из объекта

</div>

Значения свойств из объекта можно извлечь, и использовать их далее в коде как самостоятельные переменные. При извлечении свойств сам объект не меняется.

**Пример.** Извлечение свойств из объекта в отдельные константы.
```js
const user = {
  name: 'John',
  age: 30
};

const name = user.name;
const age = user.age;

console.log(name);  // 'John'
console.log(age);   // 30

// Изначальный объект не меняется
console.log(user);
// {
//   name: 'John',
//   age: 30
// }
```

<br />

Второй способ извлечения свойств — использовать деструктурирующее присваивание (деструктуризация).

Для этого, в фигурных скобках нужно указать свойства, которые необходимо извлечь из массива.

**Пример.** Пример деструктуризации.
```js
const user = {
  name: 'John',
  age: 30
};

const { name, age } = user;

console.log(name);  // 'John'
console.log(age);   // 30
```

<br />

При деструктуризации имена переменных можно менять. Для этого в фигурных скобках после названия ключа ставится двоеточие и пишется новое имя для переменной.

**Пример.** Изменение названия переменной при деструктуризации.
```js
const user = {
  name: 'John',
  age: 30
};

const { name: firstName, age: userAge } = user;

console.log(firstName);  // 'John'
console.log(userAge);   // 30

// При этом названия перед двоеточием нам доступны не будут
console.log(name);  // undefined
console.log(age);  // undefined
```





<br />

<div align="center">

### И еще про выражения

</div>

В синтаксисе средств доступа (`выражение.ключ`, `выражение[выражение]`), выражение в левой части может быть объектом, константой, переменной, функцией или любым другим кодом, который в результате вычисления возвращает объект.

**Обязательное условие: результат выражения должен быть объектом!**

Во всех примерах ниже, выражение в результате возвращает объект, из которого в дальнейшем достается свойство `name`.

**Пример.** Выражение, состоящее из объекта.
```js
console.log({ name: 'Павел' }.name);     // Павел
console.log({ name: 'Павел' }['name']);  // Павел
```

<br />

**Пример.** Выражение, состоящее из константы.
```js
const object = { name: 'Павел' };

console.log(object.name);     // Павел
console.log(object['name']);  // Павел
```

<br />

**Пример.** Выражение, состоящее из функции.
```js
function getObject() {
  return {
    name: 'Павел'
  };
}

console.log(getObject().name);
console.log(getObject()['name']);
```

<br />

Поясним последний пример:
1. Сперва запускается функция `getObject()`.
2. Функция возвращает объект.
3. Далее из этого объекта достается свойство `name`.





<br />
<br />

<div align="center">

## Методы

</div>

**Метод** — таким словом называют функцию, которая хранится в значении свойства объекта.

Функция может быть как обычной, так и стрелочной.

**Пример.** Примеры методов.
```js
const object = {
  methodName: function () {
    console.log('Это метод!');
  }
};

const secondObject = {
  anotherMethod: () => {
    console.log('И это тоже метод!');
  }
};
```

<br />

То есть когда мы говорим слово "функция" — мы подразумеваем самостоятельно написанную в коде функцию, а когда мы говорим слово "метод" — подразумеваем функцию, которая хранится в каком-то объекте.

<br />

Для вызова метода объекта, нужно обратиться к нему и написать круглые скобки.

**Пример.** Вызов метода.
```js
const user = {
  sayHi: () => {
    console.log('Привет!');
  }
};

user.sayHi();
// Привет!
```

<br />

Существует специальный короткий синтаксис для методов в объекте. Выглядит он так, словно при объявлении функции просто пропущено слово `function`.

**Пример.** Сокращенное написание метода в объекте.
```js
const user = {
  sayHi() {
    console.log('Привет!');
  }
};

user.sayHi();
// Привет!
```





<br />

<div align="center">

### Извлечение методов из объекта

</div>

Как и обычные свойства, методы можно извлекать из объекта.

**Пример** Извлечение метода из объекта.
```js
const object = {
  sayHi() {
    console.log('Привет!');
  }
};

const greeting = object.sayHi;
console.log(greeting());
// Привет!
```

<br />

**Обратите внимание!** При извлечении функции не нужно ставить круглые скобки!

Если мы поставим круглые скобки, то в константу `greeting` будет записана не функция, а результат её работы (в данном случае, `undefined`).

**Пример** Ошибка! Вместо извлечения метода, мы записали `undefined` в `greeting`.
```js
const object = {
  sayHi() {
    console.log('Привет!');
  }
};

const greeting = object.sayHi();
console.log(greeting());
// TypeError: greeting is not a function
// Такую ошибку мы получили потому,
// что в итоге попытались вызвать `undefined()`.
```





<br />
<br />

<div align="center">

## Глобальный объект `window`

</div>

Глобальный объект `window` — это обычный объект, который содержит внутри себя большое количество свойств. С помощью него мы можем узнать размеры окна браузера, прокрутку экрана, вызвать всплывающее окно, получить CSS-стили и многое, многое другое.

Объект `window` автоматически создается и заполняется при запуске JavaScript-кода движком. Для нас это означает, что объект `window` и его свойства доступны всегда и в любом месте программы.

Рассмотрение возможностей, которые дает нам `window`, мы вынесем в отдельный курс. На данном этапе нужно только лишь знать, что такой объект существует.

**Пример.** Вывод в консоль объекта `window`.
```js
console.log(window);
// ...очень много свойств...
```





<br />
<br />

<div align="center">

## Ключевое слово `this`

</div>

**Ключевое слово `this`** — это ссылка на некоторый объект. На какой именно объект будет указывать ссылка зависит от того, где и как была вызвана функция с `this` внутри себя.

Здесь правило простое:
- если функция была вызвана как метод объекта (`объект.метод()`), то `this` будет указывать на этот объект;
- во всех остальных случаях `this` будет указывать на глобальный объект `window`.





<br />

<div align="center">

### Когда `this` указывает на объект

</div>

Если вызов функции построен по синтаксису `объект.метод()` — то `this` будет указывать на этот объект.

**Пример.** Вывод `this` внутри функции, вызванной как метод объекта.
```js
const user = {
  name: 'Павел',
  age: 38,
  greeting: function () {
    console.log(this);
  }
};

user.greeting();
// Так как функция вызвана как метод объекта,
// то this указывает на этот объект:
// {
//   name: 'Павел',
//   age: 38,
//   greeting: ƒ
// }
```

<br />

**Пример.** Еще один пример, когда `this` указывает на текущий объект.
```js
const car = {
  brand: 'BMW',
  start() {
    console.log(this);
  }
};

car.start();
// {
//   brand: 'BMW',
//   start: ƒ
// }
```





<br />

<div align="center">

### Когда `this` НЕ указывает на объект

</div>

Если функция вызывается не как метод объекта (по синтаксису `функция()`) — то `this` указывает на глобальный объект.

В следующих примерах `this` будет указывать на глобальный объект `window`.

**Пример.** Вывод `this` вне функции.
```js
console.log(this);
// window
// так как this находится вне какой либо функции
```

<br />

**Пример.** Вывод `this` внутри функции, запущенной обычным образом.
```js
function doSomething() {
  console.log(this);
}

doSomething();
// window
// при синтаксисе `функция()` — this всегда указывает на глобальный объект
```

<br />

**Пример.** Вывод `this` внутри функции, запущенной обычным образом.
```js
const object = {
  name: 'John',
  sayHi: function() {
    console.log(this);
  }
};

const fn = object.sayHi;
fn();
// window
// Хоть функция и содержится в объекте, но в итоге она была
// вызвана не как метод объекта, поэтому this будет указывать на window
```

<br />

**Пример.** Вывод `this` в консоль.
```js
const object = {
  name: 'John',
  sayHi: function() {
    // Не важно где находится функция, если она вызывается
    // не как метод объекта, то this будет ссылаться на window
    function some() {
      console.log(this);
    }

    some();
  }
};

object.sayHi();
// window
```





<br />

<div align="center">

### Зачем нужен `this`

</div>

Ссылка на объект `this` полезна в случаях, когда функции требуется получить информацию об окружении, в котором она выполняется.





<br />

<div align="center">

#### Не нужно следить за названием объекта

</div>

Представьте ситуацию, когда в методе объекта нужно использовать значения текущего объекта.

**Пример.** Использование значения объекта во внутреннем методе.
```js
const user = {
  name: 'Павел',
  greeting() {
    console.log('Привет, меня зовут ' + user.name);
  }
};

user.greeting();
// Павел
```

<br />

Здесь, чтобы получить имя пользователя, мы обратились к объекту по его названию `user`.

Но что если название объекта поменяется? Тогда нам нужно будет тщательно просматривать объект, и исправлять название на актуальное.

**Пример.** Ошибка! Название объекта изменено, но во внутреннем методе название не исправлено.
```js
const guest = {
  name: 'Павел',
  greeting() {
    // объекта user больше нет!
    console.log('Привет, меня зовут ' + user.name);
  }
};

guest.greeting();
// ReferenceError: user is not defined
```

<br />

Благодаря `this`, следить за названием объекта нам больше не нужно.

**Пример.** Получение имени пользователя из контекста `this`.
```js
const user = {
  name: 'Павел',
  greeting() {
    console.log('Привет, меня зовут ' + this.name);
  }
};

user.greeting();
// Привет, меня зовут Павел
```





<br />

<div align="center">

### `this` в стрелочных функциях

</div>

У стрелочных функций отсутствует собственное значение `this`. Вместо этого, значение `this` будет браться из внешнего окружения.

**Пример.** Вывод в консоль `this` внутри стрелочной функции.
```js
const fn = () => {
  console.log(this);
};

fn();
// window
```

<br />

**Пример.** Вывод в консоль `this` внутри стрелочной функции.
```js
const object = {
  name: 'John',
  fn: () => {
    console.log(this);
  }
};

object.fn();
// window
```

<br />

**Пример.** Вывод в консоль `this` внутри стрелочной функции.
```js
// В этом примере значение this берется у внешней функции fn,
// которая была запущена как метод объекта object.
const object = {
  name: 'John',
  fn: function() {
    const arrowFn = () => {
      console.log(this);
    };
    
    arrowFn();
  }
};

object.fn();
// {
//   name: 'John',
//   fn: ƒ
// }
```





<br />

<div align="center">

### Изменение значения `this`

</div>

С помощью методов `bind()`, `call()` и `apply()` мы можем менять значение `this` в функции.

> Эти методы могут быть вызваны только у функций.





<br />

<div align="center">

#### Метод `bind()`

</div>

**Метод `bind()`** — создает новую функцию, которая в качестве значения `this` устанавливает первый переданный аргумент.

**Пример.** Использование метода `bind()`.
```js
function doSomething() {
  console.log(this);
}

const bindedFn = doSomething.bind({ name: 'Steve' });
bindedFn();
// {
//   name: 'Steve'
// }
```

<br />

**Обратите внимание!** Метод `bind()` не запускает выполнение функции и никак не меняет исходную функцию `doSomething()`. Он создает копию функции `doSomething()` и меняет в ней значение `this`. Далее копию функции мы помещаем в новую переменную `bindedFn`, которую вызываем на следующей строке.

Еще одна фишка методы `bind()` — после указания нового объекта `this` через запятую мы можем передать аргументы. Эти аргументы будут всегда доступны при вызове функции.

**Пример.** Использование метода `bind()` с передачей аргументов.
```js
function doSomething(param1, param2, param3) {
  console.log(this);
  console.log(param1);
  console.log(param2);
  console.log(param3);
}

const bindedFn = doSomething.bind({ name: 'Steve' }, 'Привязанный аргемунт 1', 'Привязанный аргумент 2');
bindedFn('Обычный аргумент');
// {
//   name: 'Steve'
// }
// Привязанный аргумент 1
// Привязанный аргумент 2
// Обычный аргумент
```

<br />

Обратите внимание на порядок связывания аргументов с параметрами. В первую очередь к параметрам будут привязаны аргументы, переданные в методе `bind()`, и лишь за ними последуют аргументы, переданные при вызове функции.





<br />

<div align="center">

#### Метод `call()`

</div>

**Метод `call()`** — вызывает функцию с набором аргументов, где первым из них будет объект для `this`.

**Пример.** Использование метода `call()`.
```js
function fn(arg1, arg2) {
  console.log(this);
  console.log(arg1);
  console.log(arg2);
}

fn.call({ name: 'John' }, 'Smith', 33);
// {
//   name: 'John'
// }
// 'Smith'
// 33
```

<br />

В отличие от метода `bind()`, метод `call()` сразу вызывает функцию без создания её копии.





<br />

<div align="center">

#### Метод `apply()`

</div>

**Метод `apply()`** — вызывает функцию с двумя аргументами: первый — объект для `this`, второй — массив аргументов для функции.

**Пример.** Использование метода `apply()`.
```js
function fn(arg1, arg2) {
  console.log(this);
  console.log(arg1);
  console.log(arg2);
}

fn.apply({ name: 'John' }, ['Smith', 33]);
// { name: 'John' }
// 'Smith'
// 33
```

<br />

Обратите внимание, что хоть аргументы и передаются в виде массива, в параметры функции они по-прежнему попадают как отдельные аргументы.

<br />

Так как в стрелочных функциях отсутствует собственный `this`, то и задать его с помощью методов `bind()`, `call()` и `apply()` нельзя.

```js
const fn = (arg1, arg2) => {
  console.log(this);
  console.log(arg1);
  console.log(arg2);
};

fn.call({ name: 'John' }, 'Smith', 33);
// window
// 'Smith'
// 33
```





<br />

<div align="center">

#### Зачем нужны `bind()`, `call()` и `apply()`?

</div>

<br />

Бывают ситуации, когда нужная ссылка для `this` может потеряться. И в таких случаях, нам на помощь приходят методы, с помощью которых мы можем вручную установить нужную нам ссылку для `this`.





<br />

<div align="center">

## Заключение

</div>

В текущей главе было рассказано про объекты и `this`. Однако, есть еще темы про объекты, которые нам предстоит покрыть в следующих главах: конфигурирование свойств, наследование и прототипы.

Но это будет в следующий раз, а сейчас:
1. Ответьте на контрольные вопросы.
2. Пройдите тесты.
3. Прорешайте задачи.





<br />

<div align="center">

## Контрольные вопросы

</div>

1. Что такое объект?
2. Зачем нужны объекты?
3. Что такое ключ?
4. Какие есть виды записей ключа? В чем их отличия?
5. Какие возможности дает запись ключа в квадратных скобках?
6. Что будет, если несколько ключей имеют одинаковое название?
7. Что такое значение свойства объекта?
8. Какие типы данных могут содержаться в значении свойства объекта?
9. Как получить значение свойства объекта?
10. Как добавить свойство в объект?
11. Как изменить значение свойства объекта?
12. Как удалить свойство из объекта?
13. Как извлечь в константу/переменную свойство объекта?
14. Что такое деструктуризация?
15. Что такое метод?
16. Как записывается короткий синтаксис метода?
17. Как извлечь метод в отдельную константу/переменную?
18. Что такое глобальный объект `window`?
19. Что такое `this`?
20. На что указывает `this`?
21. Зачем нужен `this`?
22. На что указывает `this` в стрелочных функциях?
23. Как работают методы `bind()`, `call()` и `apply()`?
24. Зачем нужны методы `bind()`, `call()` и `apply()`?
