<div align="center">

# Сброс стилей

</div>

<br />

**Сброс стилей** — это приведение стилей по-умолчанию между разными браузерами к единому варианту.

Разные браузеры выставляют разные значения стилей по-умолчанию для одних и тех же HTML-элементов. В современных реалиях, большинство разработчиков браузеров договорилось между собой и, в целом, стили можно не сбрасывать. Но чтобы обезопасить себя от неожиданностей, сброс делать нужно.

Существуют два разных подхода к сбросу стилей: Reset и Normalize.



<br />

<div align="center">

## Reset

</div>

**Reset** — подход, при котором сбрасываются вообще все стили таким образом, чтобы все элементы имели плюс-минус одинаковые стили.

Например, визуально не будет никакой разницы между элементами `<h1>`, `<h6>`, `<p>`, `<div>`. И далее мы уже сами назначаем как будут выглядеть те или иные элементы.

Самый распространенный пример сброса — `reset.css` Эрика Майера:  
[https://meyerweb.com/eric/tools/css/reset/](https://meyerweb.com/eric/tools/css/reset/)



<br />

<div align="center">

## Normalize

</div>

**Normalize** — подход, при котором стили унифицируются с сохранением особенностей HTML-элементов.

Например, визуально отличия между `<h1>`, `<h6>`, `<p>` будут, но во всех браузерах стили этих элементов будут одинаковые.

Самый распространенный пример нормализации — `normalize.css` Николаса Галлахера:  
[https://necolas.github.io/normalize.css/latest/normalize.css](https://necolas.github.io/normalize.css/latest/normalize.css)



<br />

<div align="center">

## Подключение файла сброса

</div>

Выбор между `Reset` и `Normalize` для проектов вы должны делать сами. Но какой бы подход вы ни выбрали, подключать файл со сбросом нужно перед всеми другими стилями.

**Пример 1.1.** Подключение `reset.css`.
```html
<!doctype>
<html lang="ru">
  <head>
    <title>Страница</title>
    <link rel="stylesheet" href="reset.css">
    <link rel="stylesheet" href="styles.css">
  </head>
  <body>
    <h1>Заголовок первого уровня</h1>
  </body>
</html>
```