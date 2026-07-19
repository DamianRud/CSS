# 📱 CSS `@media` — адаптивная вёрстка

## Что такое `@media`?

`@media` позволяет менять стили в зависимости от размера экрана: 💻 компьютер, 📱 планшет, 📱 телефон.

## Синтаксис

```css
@media (max-width: 768px) {
  /* стили для маленьких экранов */
}
```

`max-width: 768px` означает: **если ширина экрана 768px или меньше — применить эти стили.**

---

## Пример

Обычная версия (компьютер):

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
}
```

Адаптивная версия (телефон):

```css
@media (max-width: 768px) {
  .container {
    grid-template-columns: 1fr;
  }
}
```

**На компьютере** — три колонки: `📦 📦 📦`
**На телефоне** — одна колонка друг под другом: `📦` / `📦` / `📦`

---

## Адаптация `grid-template-areas`

**Компьютер**
```css
grid-template-areas:
  "header header header"
  "menu   main   aside"
  "footer footer footer";
```
```text
HEADER  HEADER  HEADER
MENU    MAIN    ASIDE
FOOTER  FOOTER  FOOTER
```

**Телефон**
```css
grid-template-areas:
  "header"
  "menu"
  "main"
  "aside"
  "footer";
```
```text
HEADER
MENU
MAIN
ASIDE
FOOTER
```

> ⚠️ **Количество областей в строке = количеству колонок.**
> 3 колонки (`repeat(3, 1fr)`) → `"header header header"`
> 1 колонка (`1fr`) → `"header"`

---

## Полный пример

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-areas:
    "header header header"
    "menu   main   aside"
    "footer footer footer";
}

@media (max-width: 768px) {
  .container {
    grid-template-columns: 1fr;
    grid-template-areas:
      "header"
      "menu"
      "main"
      "aside"
      "footer";
  }
}
```

---

## Как проверить адаптивность?

1. Открыть DevTools — `F12`
2. Нажать `Ctrl + Shift + M` или иконку 📱 *Toggle Device Toolbar*
3. Выбрать устройство: iPhone, Pixel, Galaxy, iPad

---

## 🧠 Главное правило

Сначала пишутся стили **для компьютера**, а затем внутри `@media` — стили **для маленьких экранов**.

```css
/* Компьютер */
.container {
  grid-template-columns: repeat(3, 1fr);
}

/* Телефон */
@media (max-width: 768px) {
  .container {
    grid-template-columns: 1fr;
  }
}
```

---

## ✅ Что изучено

- `@media`
- `max-width`
- Адаптация Grid
- Изменение `grid-template-columns`
- Изменение `grid-template-areas`
- Проверка сайта через DevTools

---

🔥 **Итог:** это один из ключевых навыков фронтенд-разработчика — современные сайты должны одинаково хорошо работать и на компьютере, и на телефоне.
