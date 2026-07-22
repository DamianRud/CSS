# 🎨 CSS Анимации

> Конспект по анимациям в CSS.

---

## 📌 Что такое анимация?

**Анимация** позволяет изменять свойства элемента **автоматически**, без действий пользователя.

Например:

- изменение цвета
- движение
- вращение
- увеличение
- исчезновение
- появление

---

## 🔄 Чем отличается `transition` от `animation`?

### `transition`

Работает **только после какого-либо действия**.

Например:

- наведение мыши (`:hover`)
- нажатие (`:active`)
- фокус (`:focus`)

```css
.button {
  transition: 0.5s;
}

.button:hover {
  transform: scale(1.1);
}
```

### `animation`

Работает **сама** — например, сразу после загрузки страницы.

```css
.box {
  animation: color 3s;
}
```

---

## 🎬 `@keyframes`

Создаёт **сценарий анимации**.

```css
@keyframes color {
  from {
    background: red;
  }

  to {
    background: blue;
  }
}
```

---

## ⏱️ `from` и `to`

Определяют **начало и конец** анимации.

```css
from {
  background: red;
}

to {
  background: blue;
}
```

Получается:

```
🔴 → 🔵
```

---

## ▶️ `animation`

Подключает анимацию.

```css
.box {
  animation: color 3s;
}
```

Где:

| Значение | Смысл |
|---|---|
| `color` | название анимации |
| `3s` | длительность |

---

## 🔁 `animation-iteration-count`

Определяет **количество повторений**.

```css
animation-iteration-count: 1;        /* один раз */
animation-iteration-count: 3;        /* три раза */
animation-iteration-count: infinite; /* бесконечно */
```

---

## ↔️ `animation-direction`

Определяет **направление** анимации.

### `normal`

```
🔴 → 🔵
🔴 → 🔵
🔴 → 🔵
```

Каждый раз начинается сначала.

### `alternate`

```
🔴 → 🔵
🔵 → 🔴
🔴 → 🔵
```

Анимация идёт вперёд, потом назад. Получается намного плавнее.

---

## ➡️ `transform: translateX()`

Перемещает элемент **по горизонтали**.

```css
transform: translateX(300px);
```

Получается:

```
⬜ → → →
```

---

## ⬇️ `transform: translateY()`

Перемещает элемент **по вертикали**.

```css
transform: translateY(100px);
```

Получается:

```
⬜
 ↓
⬜
 ↓
⬜
```

---

## 🧪 Пример анимации движения

```css
@keyframes move {
  from {
    transform: translateX(0);
  }

  to {
    transform: translateX(300px);
  }
}

.box {
  width: 100px;
  height: 100px;
  background: red;

  animation: move 3s;
  animation-iteration-count: infinite;
  animation-direction: alternate;
}
```

---

## 📍 Где используются анимации?

- Кнопки
- Карточки товаров
- Загрузчики
- Логотипы
- Меню
- Иконки
- Баннеры
- Плавное появление элементов

---

## 🐞 Частые ошибки

### ❌ Забыть создать `@keyframes`

---

### ❌ Назвать анимацию по-разному

```css
@keyframes move {
}

.box {
  animation: color 3s;
}
```

Так работать не будет — названия должны совпадать.

---

### ❌ Использовать `animation`, когда нужна только плавная смена при наведении

Для `:hover` чаще подходит `transition`.

---

## ✅ Что я запомнил

- [x] `transition` работает после действия пользователя
- [x] `animation` работает автоматически
- [x] `@keyframes` создаёт сценарий анимации
- [x] `from` — начало
- [x] `to` — конец
- [x] `animation` подключает анимацию
- [x] `animation-iteration-count` задаёт количество повторений
- [x] `infinite` — бесконечная анимация
- [x] `animation-direction: alternate` делает движение вперёд и назад
- [x] `translateX()` двигает по горизонтали
- [x] `translateY()` двигает по вертикали

---

## 🏁 Итог

После изучения анимаций я умею:

- создавать простые анимации
- менять цвет элементов
- перемещать объекты
- делать бесконечные анимации
- использовать плавное движение вперёд и назад
- понимать разницу между `transition` и `animation`
