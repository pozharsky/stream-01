<div align="center">

# Цвет и прозрачность

</div>

<br />

Цвет в CSS можно задать с помощью:
- ключевого слова;
- функции `rgb()` или `rgba()`;
- хекс-значения;
- функции `hsl()` или `hsla()`.



<br />

<div align="center">

## Ключевые слова

</div>

Цвет можно задач с помощью ключевого слова, обозначающего цвет.

Список доступных ключевых слов можно найти на сайте W3.org:  
[W3C Color keywords](https://www.w3.org/wiki/CSS/Properties/color/keywords)

**Пример 1.1.** Указание цвета через ключевое слово.

```css
div {
  color: tomato;
  background: lightblue;
  border: 4px solid silver;
}
```



<br />

<div align="center">

## Свойство `opacity`

</div>

**Свойство `opacity`** — задает всему элементу прозрачность.

Возможные значения: число от 0 до 1.

**Пример 2.1.** Пример свойства `opacity`.
```css
/*
  Эти стили сделают элемент div и весь его контент полупрозрачным.
 */
div {
  opacity: 0.5;
}
```


<br />

<div align="center">

## Функции `rgb()` и `rgba()`

</div>

Функция `rgb()` принимает три числа, которые отвечают за красный, зеленый и синий цвет. Числа могут быть в диапазоне от 0 до 255.

**Пример 3.1.** Указание цвета через функцию `rgb()`.
```css
div {
  color: rgb(255, 255, 255);        /* белый */
  background: rgb(0, 0, 0);         /* черный */
  border: 1px solid rgb(255, 0 0);  /* красный */
}
```

<br />

Функция `rgba()` содержит дополнительный четвертый параметр, который отвечает за альфа-канал (прозрачность). Альфа-канал может быть в диапазоне от 0 до 1.

**Пример 3.2.** Указание цвета с прозрачностью через функцию `rgba()`.
```css
div {
  background: rgba(0, 0, 0, .5);  /* полупрозрачный черный фон */
}
```



<br />

<div align="center">

## Хекс-значения

</div>

Цвет можно задавать через шестисимвольные хекс-значения, где первые два символа отвечают за красный, вторые — за зеленый, третьи — за синий цвета.

Символ может быть в диапазоне от 0-9 A-F.

**Пример 4.1.** Указание цвета через хекс-значение.
```css
div {
  color: #FFFFFF;             /* белый */
  background: #000000;        /* черный */
  border: 1px solid #FF0000;  /* красный */
}
```

<br />

Значение можно сократить до трех символов. В таком случае, каждый символ будет продублирован.

**Пример 4.2.** Сокращенная запись хекс-значения.
```css
div {
  color: #FFF;             /* белый, аналогичен #FFFFFF */
  background: #000;        /* черный, аналогичен #000000 */
  border: 1px solid #F00;  /* красный, аналогичен #FF0000 */
}
```

<br />

Если добавить седьмой и восьмой символы, то они будут отвечать за прозрачность.

**Пример 4.3.** Добавление прозрачности через хекс-значение.
```css
div {
  background: #00000088;  /* полупрозрачный черный фон */
}
```



<br />

<div align="center">

## Функции `hsl()` и `hsla()`

</div>

Функция `hsl()` принимает три параметра, которые отвечают за оттенок, насыщенность и яркость.

Возможные значения:
- оттенок (hue) — число от 0 до 360;
- насыщенность (saturation) — процент от 0% до 100%;
- яркость (lightness) — процент от 0% до 100%.

**Пример 5.1.** Указание цвета через функцию `hsl()`.
```css
div {
  color: hsl(0, 0%, 100%);              /* белый */
  background: hsl(0, 0%, 0%);           /* черный */
  border: 1px solid hsl(0, 100%, 50%);  /* красный */
}
```

<br />

Функция `hsla()` содержит дополнительный четвертый параметр, который отвечает за альфа-канал (прозрачность).

**Пример 5.2.** Указание цвета с прозрачностью через функцию `hsla()`.
```css
div {
  background: hsla(0, 0%, 0%, .5);  /* полупрозрачный черный фон */
}
```



<br />

<div align="center">

## Ключевое слово `transparent`

</div>

`transparent` — ключевое слово, которое делает цвет полностью прозрачным.

В отличие от свойства `opacity`, ключевое слово `transparent` влияет только на указанное свойства, а не на весь элемент.

**Пример 6.1.** Делаем фон полностью прозрачным.
```css
div {
  background: transparent;
}
```