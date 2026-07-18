# 📐 CSS Grid — конспект (часть 2)

## 1. `justify-items`

Выравнивает элементы **по горизонтали** внутри ячейки грида.

```css
justify-items: start;
```
⬅️ Прижимает к левому краю.

```css
justify-items: center;
```
🎯 Размещает по центру.

```css
justify-items: end;
```
➡️ Прижимает к правому краю.

> `justify` = горизонталь ↔️

---

## 2. `align-items`

Выравнивает элементы **по вертикали** внутри ячейки грида.

```css
align-items: start;
```
⬆️ Прижимает к верхнему краю.

```css
align-items: center;
```
🎯 Размещает по центру.

```css
align-items: end;
```
⬇️ Прижимает к нижнему краю.

> `align` = вертикаль ↕️

---

## 3. `grid-template-areas`

Создаёт схему расположения блоков на странице — вместо подсчёта колонок и строк можно просто написать их названия.

```css
.container {
  display: grid;
  grid-template-columns: 1fr 3fr;
  grid-template-rows: 100px 300px 100px;
  grid-template-areas:
    "header header"
    "menu   main"
    "footer footer";
}
```

Получится:
```text
+----------------------+
|       HEADER         |
+---------+------------+
|  MENU   |    MAIN    |
+---------+------------+
|       FOOTER         |
+----------------------+
```

---

## 4. `grid-area`

Привязывает элемент к области, указанной в `grid-template-areas`. Название после `grid-area` должно **совпадать** с названием в схеме.

```html
<header class="header">HEADER</header>
<nav class="menu">MENU</nav>
<main class="main">MAIN</main>
<footer class="footer">FOOTER</footer>
```

```css
.header { grid-area: header; }
.menu   { grid-area: menu; }
.main   { grid-area: main; }
.footer { grid-area: footer; }
```

---

## 🔁 Повторение названий = объединение колонок

```css
grid-template-areas: "header header";
```
`header` займёт **2 колонки**.

```css
grid-template-areas: "header header header";
```
`header` займёт **3 колонки**.

```css
grid-template-areas: "menu menu main";
```
```text
+---------+---------+---------+
|  MENU   |  MENU   |  MAIN   |
+---------+---------+---------+
```
`menu` занимает **2 колонки**, `main` — **1 колонку**.

---

## 🧠 Шпаргалка

| Свойство | Что делает |
|---|---|
| `display: grid` | включает Grid |
| `grid-template-columns` | создаёт колонки |
| `grid-template-rows` | создаёт строки |
| `grid-column` | сколько колонок занимает элемент |
| `grid-row` | сколько строк занимает элемент |
| `justify-items` | выравнивает по горизонтали ↔️ |
| `align-items` | выравнивает по вертикали ↕️ |
| `grid-template-areas` | создаёт схему страницы |
| `grid-area` | помещает элемент в область схемы |

---

## ✅ Что уже изучено

- `display: grid`
- `grid-template-columns`
- `repeat()`
- `1fr`
- `gap`
- `grid-column`
- `grid-row`
- `grid-template-rows`
- `justify-items`
- `align-items`
- `grid-template-areas`
- `grid-area`

---

## 📌 Как запомнить

- `justify` → горизонталь ↔️
- `align` → вертикаль ↕️
- `column` → ширина элемента
- `row` → высота элемента
- `areas` → схема страницы
- `area` → место элемента в этой схеме
