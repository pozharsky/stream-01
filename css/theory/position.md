<div align="center">

# Позиционирование

</div>

<br />

**Позиционирование** — это изменение расположения элементов в документе.

За позиционирование отвечает свойство `position` с одним из пяти значений: `static`, `relative`, `absolute`, `fixed`, `sticky`.

За решение проблем с перекрытием одним элементом другого отвечает концепция под названием контекст наложения.



<br />

<div align="center">

## `static`

</div>

**Значение `static`** (или статический элемент) — это значение по-умолчанию, при котором элемент находится в обычном состоянии и расположен в своем месте в нормальном потоке.

При задании элементам значения `static` — ничего не поменяется. Один элемент идет за другим по изученным ранее правилам.

В значении `static`, свойства `left`, `right`, `bottom`, `top` и `z-index` у элемента не работают.

**Пример 1.1.** Написание значения `static`.
```css
div {
  position: static;
}
```



<br />

<div align="center">

## `relative`

</div>

**Значение `relative`** (или относительно позиционируемый элемент) — как и `static`, располагает элемент в нормальном потоке на своем месте.

Однако с помощью свойств `left`, `right`, `top` и `bottom` — мы можем смещать элемент относительно его текущей позиции, а с помощью свойства `z-index` — менять позицию элемента по оси z.

**Пример 2.1.** Написание свойства `relative`.
```css
div {
  position: relative;
  top: 50px;
  left: 30px;
}
```



<br />

<div align="center">

## `absolute`

</div>

**Значение `absolute`** (или абсолютно позиционируемый элемент) — вырывает элемент из потока.

С помощью свойств `left`, `right`, `top` и `bottom` элемент позиционируется относительно ближайшего предка, у которого есть свойство `position` в любом значении, кроме `static`.

**Пример 3.1.** Написание значения `absolute`.
```css
div {
  position: absolute;
  top: 20px;
  left: 40px;
}
```

<br />

**Пример 3.2.** Позиционирование блока относительно родительского.
```html
<div class="parent">
  <p class="absolute">Текст</p>
</div>
```

```css
.parent {
  position: relative;
  margin: 100px;
  width: 200px;
  height: 200px;
  background: #ddd;
}

/* Этот элемент будет расположен снизу справа элемента parent */
.absolute {
  position: absolute;
  bottom: 0;
  right: 0;
}
```



<br />

<div align="center">

## `fixed`

</div>

**Значение `fixed`** — вырывает элемент из потока и позиционирует его относительно окна вьюпорта (за исключением случаев, когда у родительских элементов есть свойства `transform`, `perspective` или `filter`).

При прокрутке окна элемент всегда будет находиться в одном месте на экране.

**Пример 4.1.** Написание значения `fixed`.
```css
div {
  position: fixed;
  top: 50%;
  left: 50%;
}
```



<br />

<div align="center">

## `sticky`

</div>

**Значение `sticky`** — располагает элемент в его нормальном положении в документе. Далее позиционирует элемент в зависимости от прокрутки ближайшего прокручиваемого предка.

Для работы значения `sticky` у элемента должно быть задано свойство `top` (в значении отличном от `auto`).

**Пример 5.1.** Написание значения `sticky`.
```css
/* Теперь элемент будет при прокрутке прикрепляться к верху экрана */
div {
  position: sticky;
  top: 0;
}
```

<br />

В примере выше, элемент будет вести себя как обычно. Однако, когда прокрутка экрана достигнет края элемента, `sticky` прикрепится к границе экрана и будет прокручиваться вместе с экраном до тех пор, пока не встретит край родительского элемента.

То же самое работает и при горизонтальной прокрутке. Но для этого вместо свойства `top` у элемента должно быть задано свойство `left`.

**Пример 5.2.** Написание значения `sticky`.
```css
/*
  Теперь элемент будет при горизонтальной прокрутке
  прикрепляться к левой части экрана
 */
div {
  position: sticky;
  left: 0;
}
```



<br />

<div align="center">

## `z-index`

</div>

**Свойство `z-index`** — позиционирует элемент по оси z. Чем выше значение — тем выше элемент над другими.

Данное свойство работает со всеми элементами, у которых задано свойство `position` в любом значении, кроме `static`.

**Пример 6.1.** Позиционирование одного элемента над другим.
```html
<div class="block-1">Элемент 1</div>
<div class="block-2">Элемент 2</div>
```

```css
.block-1,
.block-2 {
  width: 200px;
  height: 200px;
  position: fixed;
}

.block-1 {
  top: 50px;
  left: 50px;
  z-index: 2;
}

.block-2 {
  top: 100px;
  left: 100px;
  z-index: 1;
}
```

<br />

В примере выше, элемент `block-1` будет расположен над элементом `block-2`, так как `z-index: 2` больше чем `z-index: 1`.



<br />

<div align="center">

## Контекст наложения

</div>

**Контекст наложения** — это концепция трехмерного расположения HTML-элементов по оси z.

Для соседних элементов контекст наложения работает очень просто: чем больше значение `z-index`, тем выше элемент.

**Пример 7.1.** Контекст наложения для соседних элементов.
```css
.block-1 {
  position: fixed;
  z-index: 4;
}

.block-2 {
  position: fixed;
  z-index: 2;
}
```

<br />











