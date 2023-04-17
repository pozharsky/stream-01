<div align="center">

# Наследование

</div>

<br />

**Наследование** — это правило, которое определяет, какие значения будут у свойств, если их не задать напрямую на элементе.

Некоторые свойства передаются в дочерние элементы.

**Пример 1.1.** Передача свойств `font-size` и `color` от `<div>` к `<p>`.
```html
<div>
  <p>Параграф</p>
</div>
```
```css
div {
  font-size: 20px;
  color: red;
}
```

<br />

В примере выше, хоть мы и не задавали никаких стилей параграфу, но его размер шрифта стал равен `20px`, а цвет текста теперь красный. В таком случае говорят, что параграф унаследовал значения свойств `font-size` и `color`.

Некоторые свойства наследуются, а некоторые нет. Чтобы узнать наверняка, информация о наследовании конкретных свойств доступна в большинстве справочников с CSS-свойствами.

Примеры наследуемых свойств:
- `color`;
- `font`, включая `font-size`, `font-family` и т.д.

Примеры ненаследуемых свойств:
- `background`;
- `width`;
- `height`;
- `display`.