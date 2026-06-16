---
name: blue-design
description: >
  UI-кит "Liquid Glass / Apple Frosted" — набор стеклянных модулей с backdrop-blur
  для применения поверх ЛЮБОГО дизайна и ЛЮБОЙ палитры. Не диктует цвета, шрифты или
  композицию. Содержит только компоненты: glass-card, notched-card с выступающей иконкой,
  pill-навигация, pill-кнопки, угловая стрелка "↗", social-proof pill с аватарами,
  stat-card, glass-tag, glass-badge, glass-divider, glass-tooltip, glass-modal.
  Используй ВСЕГДА когда пользователь просит — "blue design", "Блу дизайн", "стеклянные
  модули", "liquid glass", "frosted glass", "стеклянные плашки", "glassmorphism",
  "Apple стиль", "Apple glass", "сделай стеклянным", "переведи в Apple стиль",
  "примени стеклянный UI", "наложи glass-кит". Применяй компоненты ПОВЕРХ существующего
  дизайна, сохраняя его палитру, типографику и контент. Заменяй только UI-элементы
  на стеклянные эквиваленты из кита.
---

# Liquid Glass UI Kit — "Apple Frosted"

Чистый набор стеклянных компонентов. Без цветов, шрифтов, композиций.
Применяется поверх любого дизайна — палитра наследуется от родителя, контент остаётся.

---

## КОГДА ПРИМЕНЯТЬ

Триггеры — любой из:
- "blue design" / "блу дизайн"
- "стеклянные модули" / "стеклянные плашки"
- "liquid glass" / "frosted glass" / "glassmorphism"
- "сделай Apple-стиль" / "переведи в Apple glass"
- "наложи glass UI" / "стеклянный UI-кит"

Что делать: брать существующие блоки сайта/презентации и **заменять их UI-обёртки** на стеклянные модули из кита ниже. Палитру, шрифты, текст, расположение секций — **не трогать**.

---

## БАЗОВЫЙ КЛАСС (ядро всех модулей)

```css
.glass{
  background: rgba(255,255,255,.18);
  backdrop-filter: blur(24px) saturate(140%);
  -webkit-backdrop-filter: blur(24px) saturate(140%);
  border: 1px solid rgba(255,255,255,.45);
  border-radius: 22px;
  box-shadow:
    inset 0 1px 0 rgba(255,255,255,.6),
    0 20px 40px -20px rgba(0,0,0,.18);
}
```

Три обязательных свойства, которые делают стекло «Apple», а не плоский glassmorphism:
1. `backdrop-filter` с `saturate(140%)` — насыщение прокрашивает фон под плашкой
2. `inset 0 1px 0 rgba(255,255,255,.6)` — внутренний highlight сверху (имитация преломления)
3. Большая мягкая drop-shadow вниз

**Тёмная вариация** (для тёмного фона):
```css
.glass--dark{
  background: rgba(20,20,28,.35);
  border: 1px solid rgba(255,255,255,.12);
  box-shadow:
    inset 0 1px 0 rgba(255,255,255,.12),
    0 20px 40px -20px rgba(0,0,0,.5);
}
```

---

## КОМПОНЕНТЫ КИТА

### 1. Glass Card (базовая карточка)

```html
<div class="glass card">
  <div class="card-corner">↗</div>
  <!-- любой контент -->
</div>
```
```css
.card{ padding:22px; position:relative; }
```

### 2. Notched Card (с иконкой через верх)

Иконка 64×64 поднимается на `-30px`, создавая «вырез» в карточке.

```html
<div class="glass card notched">
  <div class="icon-bubble"><!-- icon --></div>
  <div class="card-corner">↗</div>
  <div class="notched-inner"><!-- content --></div>
</div>
```
```css
.notched{ overflow:visible; }
.icon-bubble{
  position:absolute; left:18px; top:-30px;
  width:64px; height:64px; border-radius:18px;
  background: linear-gradient(160deg, #fff, rgba(255,255,255,.6));
  box-shadow: 0 14px 30px -10px rgba(0,0,0,.25);
  border: 1px solid rgba(255,255,255,.8);
  display: grid; place-items: center;
}
.notched-inner{ padding-top:42px; }
```

### 3. Угловая стрелка ↗ (corner arrow)

Маленький круг 30×30 в правом верхнем углу любой glass-карточки. Сигнал «интерактивно».

```html
<div class="card-corner">↗</div>
```
```css
.card-corner{
  position:absolute; top:14px; right:14px;
  width:30px; height:30px; border-radius:50%;
  background: rgba(255,255,255,.45);
  border: 1px solid rgba(255,255,255,.6);
  display: grid; place-items: center;
  font-size: 14px; cursor: pointer;
}
```

### 4. Pill Nav (стеклянное меню)

Горизонтальное меню в стеклянной пилюле с активным состоянием.

```html
<nav class="glass pill-nav">
  <a href="#" class="active">home</a>
  <a href="#">about</a>
  <a href="#">services</a>
</nav>
```
```css
.pill-nav{
  display:inline-flex; gap:8px; align-items:center;
  padding:6px; border-radius:999px;
}
.pill-nav a{
  padding:8px 16px; border-radius:999px;
  text-decoration:none; font-size:14px;
  color: inherit;
}
.pill-nav a.active{
  background:#fff; color:#111;
  box-shadow: 0 2px 8px rgba(0,0,0,.12);
}
```

### 5. Pill Button (стеклянная кнопка)

```html
<a class="glass pill-btn">Resources</a>
<a class="glass pill-btn pill-btn--solid">Get started</a>
```
```css
.pill-btn{
  display:inline-flex; align-items:center; gap:10px;
  padding:10px 20px; border-radius:999px;
  text-decoration:none; font-size:14px;
  color: inherit;
}
.pill-btn--solid{
  background:#fff; color:#111;
  box-shadow: 0 8px 20px -10px rgba(0,0,0,.25);
  border-color: transparent;
}
.pill-btn .dot{
  width:30px; height:30px; border-radius:50%;
  background: rgba(255,255,255,.22);
  display:grid; place-items:center;
}
```

### 6. Social Proof Pill (аватары + счётчик)

```html
<div class="glass proof-pill">
  <div class="avatars">
    <span></span><span></span><span></span><span></span>
  </div>
  <span class="proof-text">Active users <b>+323</b></span>
</div>
```
```css
.proof-pill{
  display:inline-flex; align-items:center; gap:10px;
  padding:6px 16px 6px 6px; border-radius:999px;
}
.avatars{ display:flex; }
.avatars span{
  width:34px; height:34px; border-radius:50%;
  border:2px solid #fff; margin-left:-8px;
  background-size: cover; background-position: center;
}
.avatars span:first-child{ margin-left:0; }
```

### 7. Stat Card (карточка с большой цифрой)

```html
<div class="glass card stat-card">
  <div class="card-corner">↗</div>
  <div class="stat-num">42<span class="stat-unit">%</span></div>
  <div class="stat-sub">Sub-caption inherits parent color</div>
</div>
```
```css
.stat-num{ font-size: 88px; line-height:.9; font-weight:300; letter-spacing:-.02em; }
.stat-unit{ font-size: 48px; margin-left:4px; }
.stat-sub{ font-size: 12px; line-height:1.4; margin-top:8px; max-width:220px; opacity:.85; }
```

### 8. Glass Tag (пилюля-тег)

Маленькая прозрачная плашка для меток (категория, статус).

```html
<span class="glass-tag">Single Origin</span>
```
```css
.glass-tag{
  display:inline-block; font-size:11px;
  padding:5px 12px; border-radius:999px;
  background: rgba(255,255,255,.55);
  border: 1px solid rgba(255,255,255,.7);
  backdrop-filter: blur(8px);
}
```

### 9. Glass Badge (уведомление-кружок)

```html
<span class="glass-badge">3</span>
```
```css
.glass-badge{
  display:inline-grid; place-items:center;
  min-width:22px; height:22px; padding:0 6px;
  border-radius:999px; font-size:11px; font-weight:600;
  background: rgba(255,255,255,.7);
  border: 1px solid rgba(255,255,255,.8);
  backdrop-filter: blur(8px);
}
```

### 10. Glass Divider (стеклянная линия)

```html
<hr class="glass-divider" />
```
```css
.glass-divider{
  border: 0; height: 1px;
  background: linear-gradient(90deg,
    transparent, rgba(255,255,255,.6), transparent);
  margin: 32px 0;
}
```

### 11. Glass Tooltip (всплывающая подсказка)

```html
<span class="glass tooltip">Hint text</span>
```
```css
.tooltip{
  display:inline-block; padding:8px 12px;
  border-radius:12px; font-size:12px;
  pointer-events:none;
}
```

### 12. Glass Modal / Sheet

Полноразмерное стекло поверх дим-оверлея.

```html
<div class="glass-backdrop">
  <div class="glass modal">…</div>
</div>
```
```css
.glass-backdrop{
  position:fixed; inset:0; z-index:50;
  background: rgba(0,0,0,.25);
  backdrop-filter: blur(12px);
  display:grid; place-items:center;
}
.modal{
  width:min(560px, 92vw);
  padding:28px;
  border-radius:24px;
}
```

### 13. Glass Toolbar / Dock

Нижний/верхний бар с иконками — заменяет mobile tab-bar или sticky header.

```html
<div class="glass dock">
  <button>⌂</button><button>◎</button><button>✦</button><button>☰</button>
</div>
```
```css
.dock{
  display:inline-flex; gap:6px;
  padding:8px; border-radius:999px;
}
.dock button{
  width:44px; height:44px; border:0;
  border-radius:50%; background:transparent;
  cursor:pointer; font-size:18px;
}
.dock button:hover{ background: rgba(255,255,255,.35); }
```

### 14. Icon Bubble (иконка-плитка standalone)

Тот же элемент, что в notched-card, но как самостоятельный компонент рядом с текстом.

```html
<div class="icon-bubble"><span class="swirl"></span></div>
```
```css
.swirl{
  width:36px; height:36px; border-radius:50%;
  background: conic-gradient(from 200deg, #4a7cff, #5fb8ff, #c8dcff, #4a7cff);
  filter: blur(.3px);
}
```

> `swirl` использует синий conic — это единственный «цвет» в ките, потому что это **деталь иконки**, не палитра дизайна. Замени hue под бренд.

### 15. Ghost Backdrop (мега-серифное слово на фоне)

Не glass-модуль, но часто используется в паре. Применяй опционально.

```html
<div class="ghost">BRAND</div>
```
```css
.ghost{
  position:absolute; pointer-events:none; user-select:none;
  font-size: clamp(180px, 26vw, 380px);
  line-height:.85; letter-spacing:-.02em;
  color: rgba(255,255,255,.5);
  font-family: inherit;
}
```

---

## ПРАВИЛА ПРИМЕНЕНИЯ

1. **Кит — оверлей, не редизайн.** Цвета, шрифты, размеры текста, расположение секций — наследуются от исходного сайта. Меняй только обёртки UI-элементов.
2. **Под стеклом должен быть градиент или фото.** Стекло на плоском flat-фоне выглядит как мутное окно. Если фон родителя плоский — добавь под секцию radial-gradient или фото-блюр.
3. **Обязательный inset highlight + drop shadow** — без них стекло становится плоским glassmorphism нулевых.
4. **Не лепи стекло на стекле.** Максимум 2 уровня вложенности (карточка внутри карточки). Глубже — теряется читаемость.
5. **Радиусы фиксированы.** Карточки — 22px (или 24-28 для крупных). Pill-элементы — 999px. Иконки-плитки — 18px. Бейджи — 999px. Не отходи.
6. **Стрелка «↗»** ставится на любую интерактивную glass-карточку. Не интерактивную — без стрелки.
7. **Notched-карточка** — максимум 1-2 в ряду из 3-х. Иначе ритм ломается.
8. **Контент-первый.** Если контент карточки длинный — backdrop-filter может фризить браузер на слабых машинах. Тогда заменяй на `background: rgba(255,255,255,.7)` без blur.

---

## КАК ПРИМЕНЯТЬ ПОВЕРХ СУЩЕСТВУЮЩЕГО САЙТА

Алгоритм:
1. Прочитай текущий сайт. Определи UI-элементы: nav, кнопки, карточки фич, social-proof, статы, теги, модалки.
2. Сопоставь каждый с компонентом из кита (1→pill-nav, 2→pill-btn, 3→glass card+notched, 4→proof-pill, 5→stat-card, 6→glass-tag, 7→glass-modal).
3. Замени HTML/CSS-обёртки этих элементов. **Не трогай:** заголовки, body-текст, изображения, палитру, шрифты, grid-композицию.
4. Под секциями, где появилось стекло, проверь фон — если плоский, добавь градиент или фото-подложку.
5. Добавь corner-arrow на интерактивные карточки, glass-tag на категории, proof-pill для социалпруфа.

---

## ЧЕКЛИСТ

- [ ] У каждой glass-обёртки есть `backdrop-filter: blur(24px) saturate(140%)`
- [ ] Inset highlight `inset 0 1px 0 rgba(255,255,255,.6)` на каждой карточке
- [ ] Drop shadow вниз на каждой карточке
- [ ] Border 1px полупрозрачный белый
- [ ] Радиусы соответствуют (22 / 999 / 18)
- [ ] Под стеклом не плоский цвет, а градиент/фото
- [ ] Corner-arrow только на интерактивных
- [ ] Шрифты и палитра исходного сайта не тронуты
- [ ] Не больше 2 уровней вложенности стекла
