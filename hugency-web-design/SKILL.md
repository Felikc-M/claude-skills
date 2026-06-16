---
name: hugency-web-design
description: >
  Фирменный визуальный код HUGENCY — премиум dark + warm orange. Полная дизайн-система
  для лендингов, презентаций, дашбордов, креативов: палитра (чёрный фон + оранжевый
  градиент), типографика Vela Sans, Liquid Glass карточки с искровой подсветкой
  на hover (conic-gradient + mask-composite XOR), оранжевый em-градиент в H2,
  hero full-bleed паттерн, manifesto strike-through, section eyebrow с номером,
  стеклянные сетки 3×2 / 6×1. Используй ВСЕГДА когда пользователь упоминает —
  "Hugency style", "стиль Hugency", "как на лендинге Hugency", "фирменный стиль
  Hugency", "hugency-design", "сделай в стиле Hugency", "визуальный код Hugency",
  "оранжево-чёрный премиум", "Vela Sans + orange", "стеклянные карточки с искрами",
  "Liquid Glass Hugency", "оранжевые искры на hover". Применяй полный код или
  отдельные паттерны (glass card, spark hover, H2 orange-em, hero, manifesto).
  НЕ путать с blue-design — там цвет-нейтральный, без бренд-палитры.
---

# 🟧 HUGENCY Web Design System

> Премиум dark + warm orange. Минимализм с искровыми акцентами.
> Источник истины: live RU-лендинг `hugency-offer.vercel.app` / `www.hugency.ai/ru/`.

---

## КОГДА ПРИМЕНЯТЬ

Триггеры — любой из:
- «в стиле Hugency» / «hugency style» / «фирменный стиль Hugency»
- «как на лендинге Hugency»
- «оранжево-чёрный премиум»
- «Vela Sans + оранжевые искры»
- «стеклянные карточки Hugency»
- Любая работа с проектами / макетами / презентациями для **HUGENCY** (AI-driven performance marketing студия)

**НЕ путать с `blue-design`** — там чисто стеклянные модули без бренд-цветов. Здесь — полный фирменный код.

---

## 1. ЦВЕТОВАЯ ПАЛИТРА

```css
:root {
  /* === Фон (всегда тёмный) === */
  --bg-0: #000000;   /* основной чёрный */
  --bg-1: #050505;   /* почти-чёрный */
  --bg-2: #0a0a0a;   /* deep dark */

  /* === Акценты (оранжевый градиент warm) === */
  --accent-1: #FF7A3D;   /* основной "spark" оранжевый */
  --accent-3: #E55A1F;   /* mid — глубже */
  --accent-5: #B84415;   /* deep — тёмно-оранжевый */

  /* === Ember (оранжевый градиент для <em> в заголовках) === */
  --ember-1: #FF9A55;   /* highlight — светлый тёплый оранжевый */
  --ember-3: #FF7A3D;   /* mid — основной оранжевый */
  --ember-5: #E55A1F;   /* deep — чуть темнее оранжевый */

  /* === Текст === */
  --text:      #f4f4f0;   /* основной */
  --text-soft: #d8d8d2;   /* мягкий */
  --text-dim:  #bcbcb4;   /* тусклый */
  --text-mute: #a4a49c;   /* приглушённый */

  /* === Glass tokens === */
  --glass-bg:       rgba(255, 255, 255, 0.03);
  --glass-bg-hover: rgba(255, 255, 255, 0.05);
  --glass-border:   rgba(255, 255, 255, 0.12);

  /* === Spark (искры на hover) === */
  --spark-color: var(--accent-1);   /* #FF7A3D */
  --spark-hot:   #FFD2A0;            /* светлый пик */
}
```

**Правила:**
- ✅ Фон страницы — `radial-gradient(ellipse 80% 60% at 50% 50%, #1a1a1c 0%, #0a0a0b 60%, #050505 100%)` или чистый `#000` для hero
- ✅ Оранжевый — только как акцент: spark, eyebrow, ссылки, кнопки. **Никогда** не залить им большие площади
- ❌ Не добавлять синие/зелёные/фиолетовые акценты — только тёплая палитра
- ❌ Не использовать `bg` ярче `#1a1a1c` — теряется премиальность

---

## 2. ТИПОГРАФИКА

**Шрифт:** `Vela Sans` (variable, weights 300–700)
**Fallback:** `"SF Pro Display", -apple-system, BlinkMacSystemFont, "Inter", sans-serif`

```css
@font-face {
  font-family: 'Vela Sans';
  src: url('fonts/VelaSans-GX.ttf') format('truetype-variations');
  font-weight: 100 900;
  font-style: normal;
  font-display: swap;
}

body {
  font-family: "Vela Sans", "SF Pro Display", -apple-system, BlinkMacSystemFont, "Inter", sans-serif;
  -webkit-font-smoothing: antialiased;
  color: var(--text);
}
```

### Шкала размеров

| Элемент | Размер | Вес | Letter-spacing | Line-height |
|---|---|---|---|---|
| **H1 / Hero** | `clamp(17px, 22px, 22px)` | 400 | -0.02em | 1.25 |
| **H2 (section)** | `clamp(36px, 5.8vw, 64px)` | 500 | -0.035em | 0.9 |
| **H3 (card)** | 18–20px | 600 | -0.005em | 1.35 |
| **Body** | 14.5–17px | 400 | normal | 1.45–1.55 |
| **Eyebrow** | 12px | 600 | 0.18em UPPERCASE | 1 |
| **Stats (цифры)** | clamp(30–60px) | **300 (Light!)** | -0.04em | 1 |

> 🔑 Цифры всегда **Light 300** — это опровергает «инфоцыганский толстый infomarketing-look». Главная фирменная штука в типографике.

### H2 с orange-em (фирменный приём)

```html
<h2>Система, которая превращает контент в <em>деньги</em></h2>
```

```css
h2 {
  font-family: "Vela Sans", sans-serif;
  font-size: clamp(36px, 5.8vw, 64px);
  font-weight: 500;
  letter-spacing: -0.035em;
  line-height: 0.9;
  margin-bottom: 28px;
  max-width: 920px;
  color: var(--text);
}

h2 em {
  font-style: normal;   /* убираем дефолтный курсив */
  font-weight: 500;
  background: linear-gradient(135deg, var(--ember-1), var(--ember-3), var(--ember-5));
  -webkit-background-clip: text;
          background-clip: text;
  -webkit-text-fill-color: transparent;
          color: transparent;
}
```

---

## 3. LIQUID GLASS CARDS (универсальный паттерн)

Используется **везде**: feature-карточки, stat-cells, manifesto pills, H-Framework шаги, why-cells.

```css
.glass-card {
  position: relative;
  border-radius: 22px;
  background: var(--glass-bg);
  backdrop-filter: blur(28px) saturate(140%);
  -webkit-backdrop-filter: blur(28px) saturate(140%);
  border: 1px solid var(--glass-border);
  box-shadow:
    inset 0 1px 0 rgba(255, 255, 255, 0.14),   /* верхний highlight стекла */
    0 18px 36px -12px rgba(0, 0, 0, 0.4);
  overflow: hidden;
  transition:
    transform 0.45s cubic-bezier(.2, .7, .2, 1),
    border-color 0.35s ease,
    background 0.4s ease;
}

.glass-card:hover {
  transform: translateY(-4px);
  border-color: rgba(255, 122, 61, 0.45);
  background: var(--glass-bg-hover);
}
```

**Правила:**
- ✅ `backdrop-filter` требует полупрозрачный bg (0.03–0.06)
- ✅ Тёмный градиентный фон страницы обязателен — иначе blur не виден
- ✅ Дублируй `-webkit-` префиксы (Safari)
- ❌ Не применяй `transform: scale()` на hover — ломает layout в grid

---

## 4. EDGE SPARKS (фирменный hover-эффект) ⭐

> **Главная визуальная отличка HUGENCY** — на hover вдоль рамки карточки загораются 2 искры в противоположных углах. Реализовано через `conic-gradient` + `mask-composite: xor`.

### CSS
```css
.glass-card::after {
  content: '';
  position: absolute;
  inset: 0;
  padding: 1px;                  /* толщина искровой обводки */
  border-radius: inherit;
  background: conic-gradient(
    from 0deg,
    transparent 0deg, transparent 38deg,
    var(--spark-color) 52deg,
    var(--spark-hot)   65deg,
    var(--spark-color) 80deg,
    transparent 96deg, transparent 218deg,
    var(--spark-color) 232deg,
    var(--spark-hot)   245deg,
    var(--spark-color) 260deg,
    transparent 276deg, transparent 360deg
  );
  -webkit-mask:
    linear-gradient(#000 0 0) content-box,
    linear-gradient(#000 0 0);
          mask:
    linear-gradient(#000 0 0) content-box,
    linear-gradient(#000 0 0);
  -webkit-mask-composite: xor;
          mask-composite: exclude;
  pointer-events: none;
  opacity: 0;
  transition: opacity 0.5s ease;
  z-index: 1;
}

.glass-card:hover::after { opacity: 1; }

/* Контент карточки — над искрами */
.glass-card > * {
  position: relative;
  z-index: 2;
}
```

### Как читать углы conic-gradient
- `52°–80°` — искра в правом-верхнем углу (1-й квадрант)
- `232°–260°` — искра в левом-нижнем углу (3-й квадрант)
- Можно сдвинуть оба парных значения на одно число градусов чтобы крутить искры по периметру

### КРИТИЧНО — что НЕ менять
- ❌ `mask-composite: xor` + два mask-слоя — сердце эффекта
- ❌ `padding: 1px` на `::after` — толщина искры
- ❌ `pointer-events: none` — иначе hover ломается
- ❌ z-index слои (фон / искры=1 / контент=2)

---

## 5. ГРИД-СЕТКА LIQUID GLASS (6 ячеек / 3×2)

Паттерн «6 причин» — карточки склеены тонкими линиями, искры подсвечивают активную.

```html
<div class="glass-grid">
  <div class="glass-cell">
    <div class="cell-num">1</div>
    <div class="cell-title">Заголовок</div>
    <div class="cell-desc">Описание ячейки.</div>
  </div>
  <!-- × 6 -->
</div>
```

```css
.glass-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 0;                                /* ячейки склеены */
  border-radius: 22px;
  overflow: hidden;
  background: var(--glass-bg);
  backdrop-filter: blur(28px) saturate(140%);
  border: 1px solid var(--glass-border);
}

.glass-cell {
  position: relative;
  padding: 22px 30px 24px;
  border-right:  1px solid rgba(255, 255, 255, 0.10);
  border-bottom: 1px solid rgba(255, 255, 255, 0.10);
  overflow: hidden;
  transition: background 0.4s ease;
}

.glass-cell:hover { background: rgba(255, 255, 255, 0.025); }

/* Убираем лишние границы у крайних ячеек */
.glass-grid .glass-cell:nth-child(3n)        { border-right:  none; }
.glass-grid .glass-cell:nth-last-child(-n+3) { border-bottom: none; }

/* Искры — тот же ::after из §4 */
.glass-cell::after { /* ... copy from §4 ... */ }
.glass-cell:hover::after { opacity: 1; }

/* Номер (например "1") — оживает на hover */
.cell-num {
  position: relative;
  z-index: 2;
  font-size: clamp(30px, 2.6vw, 42px);
  font-weight: 700;
  color: rgba(255, 255, 255, 0.72);
  margin-bottom: 14px;
  letter-spacing: -0.04em;
  transition: color 0.4s ease, transform 0.4s cubic-bezier(.2,.7,.2,1);
}
.glass-cell:hover .cell-num {
  color: var(--accent-3);
  transform: scale(1.12);
  transform-origin: left center;
}

/* Адаптив */
@media (max-width: 900px) {
  .glass-grid { grid-template-columns: repeat(2, 1fr); }
  .glass-grid .glass-cell:nth-child(3n)        { border-right: 1px solid rgba(255,255,255,0.10); }
  .glass-grid .glass-cell:nth-child(2n)        { border-right: none; }
  .glass-grid .glass-cell:nth-last-child(-n+3) { border-bottom: 1px solid rgba(255,255,255,0.10); }
  .glass-grid .glass-cell:nth-last-child(-n+2) { border-bottom: none; }
}
@media (max-width: 600px) {
  .glass-grid { grid-template-columns: 1fr; }
  .glass-grid .glass-cell { border-right: none !important; border-bottom: 1px solid rgba(255,255,255,0.10) !important; }
  .glass-grid .glass-cell:last-child { border-bottom: none !important; }
}
```

---

## 6. SECTION EYEBROW (нумерация секций)

Над каждым H2 — eyebrow с номером секции:

```html
<div class="section-head">
  <div class="section-eyebrow">
    <span class="num">05</span>
    <span class="label">H-Framework</span>
  </div>
  <h2>Система, которая превращает контент в <em>деньги</em></h2>
</div>
```

```css
.section-eyebrow {
  display: flex;
  align-items: baseline;
  gap: 16px;
  margin-bottom: 18px;
}
.section-eyebrow .num {
  font-family: "Vela Sans", sans-serif;
  font-weight: 400;
  color: var(--ember-3);
  font-size: clamp(40px, 5vw, 64px);
  letter-spacing: -0.04em;
  font-feature-settings: "tnum";
}
.section-eyebrow .label {
  font-family: "Vela Sans", sans-serif;
  font-weight: 500;
  color: var(--text-soft);
  font-size: 13px;
  letter-spacing: 0.18em;
  text-transform: uppercase;
}
```

---

## 7. MANIFESTO STRIKE PATTERN

Фирменный приём — зачёркнутое слово через `.strike` с псевдо-линией.

```html
<h2 class="manifesto-h2">
  Мы не продаём <span class="strike">контент</span>.<br>
  Мы продаём <span class="money">прибыль</span>.
</h2>
```

```css
.manifesto-h2 {
  font-family: "Vela Sans", sans-serif;
  font-size: clamp(36px, 5.8vw, 64px);
  font-weight: 500;
  letter-spacing: -0.035em;
  line-height: 1.05;
  color: var(--text);
}

.manifesto-h2 .strike {
  position: relative;
  color: rgba(255, 255, 255, 0.42);
  font-weight: 400;
}
.manifesto-h2 .strike::after {
  content: "";
  position: absolute;
  left: -2%;
  right: -2%;
  top: 52%;
  height: 1px;
  background: rgba(255, 255, 255, 0.55);
  transform: rotate(-3deg);
}

.manifesto-h2 .money {
  color: var(--text);   /* белый — НЕ оранжевый, акцент через контекст */
  font-weight: 500;
}
```

---

## 8. HERO FULL-BLEED PATTERN

Hero растягивается на 100vw (за пределы wrap):

```html
<header class="hero">
  <div class="hero-3d">
    <img src="HERO_BACK.png" alt="">   <!-- bg image -->
  </div>
  <h1 class="hero-headline">
    Мы превращаем ИИ-контент<br>
    в канал <em>лидов и продаж</em><br>
    через Reels, YouTube, TikTok<br>
    по методологии <em>H-Framework</em>
  </h1>
  <a href="#" class="hero-btn-primary">Получить прогноз <span class="arrow">›</span></a>
</header>
```

```css
.hero {
  position: relative;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 80px 48px;
  overflow: hidden;
  isolation: isolate;
}

.hero::before {
  content: "";
  position: absolute;
  top: 0;
  bottom: 0;
  left: calc(50% - 50vw);   /* выходим за wrap */
  right: calc(50% - 50vw);
  width: 100vw;
  background: url('HERO_BACK_OR.png') center/cover no-repeat;
  z-index: -1;
}

.hero-headline {
  font-family: "Vela Sans", sans-serif;
  font-size: clamp(17px, 1.6vw, 22px);
  font-weight: 400;
  color: rgba(255, 255, 255, 0.75);
  letter-spacing: -0.01em;
  line-height: 1.45;
  max-width: 600px;
}
.hero-headline em {
  font-style: normal;
  background: linear-gradient(135deg, var(--ember-1), var(--ember-3), var(--ember-5));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.hero-btn-primary {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 14px 24px;
  border-radius: 100px;
  background: var(--text);
  color: var(--bg-0);
  font-weight: 600;
  font-size: 15px;
  text-decoration: none;
  transition: transform 0.3s ease, background 0.3s ease;
}
.hero-btn-primary:hover {
  transform: translateY(-2px);
  background: var(--accent-1);
  color: var(--text);
}
```

---

## 9. КОНТЕЙНЕР И GRID

```css
.wrap {
  max-width: 1080px;     /* основной контейнер */
  margin: 0 auto;
  padding: 80px 48px;
}

@media (max-width: 768px) {
  .wrap { padding: 60px 20px; }
}
```

**Breakpoints:**
- `1280px` — desktop wide
- `1024px` — desktop
- `900px` — tablet (grid 3→2)
- `600px` — mobile (grid 2→1)
- `375px` — mobile small

---

## 10. АНИМАЦИИ И ДВИЖЕНИЕ

```css
/* Стандартные timing */
transition: <prop> 0.45s cubic-bezier(.2, .7, .2, 1);  /* для transform / hover-карточек */
transition: <prop> 0.35s ease;                          /* для color / border */
transition: <prop> 0.5s ease;                           /* для opacity / искр */

/* Reduced motion — обязательно */
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```

**Правила:**
- ✅ `transform` + `opacity` — единственное что анимируем (performance)
- ✅ Микро-движения 150–500ms
- ❌ Никаких `width / height / margin` анимаций
- ❌ Никаких `scale()` на hover в grid (ломает layout соседей)

---

## 11. ИКОНКИ

- **Только SVG** (heroicons / lucide / собственные)
- **Никаких emoji-иконок в UI** (можно в текстовом маркдауне в данной инструкции, но не в продакшн UI)
- Размер по умолчанию: `24×24` viewBox, отображение `w-5 h-5` или `w-6 h-6`
- Stroke-only иконки: `stroke-width: 2`, `stroke-linecap: round`, `stroke-linejoin: round`

---

## 12. AI ASSET GENERATION (Higgsfield Nano Banana Pro)

Когда нужны 3D-ассеты для hero / шагов / иллюстраций — используй Higgsfield CLI с этим промпт-шаблоном:

```
Premium 3D product render on pure black background, warm orange accent lighting
only from the bottom-left, [SUBJECT DESCRIPTION], no text, no labels,
ultra-clean composition, no distracting elements in upper-right area (text overlay zone),
4K cinematic, soft volumetric light, dust particles, slight depth-of-field,
photoreal materials.
```

Команда:
```bash
higgsfield generate create text2image_nano_banana_pro \
  --prompt "<promt>" --quality 2k --wait
```

---

## 13. ANTI-PATTERNS (что не делать)

| ❌ Don't | ✅ Do |
|---|---|
| `background: rgba(255,255,255,0.10)` в light mode | На белом фоне glass почти невидим — Hugency только dark |
| `border-image` для анимируемой обводки | `::after` + `conic-gradient` + `mask-composite: xor` |
| Emoji-иконки (🎨 🚀 ⚙️) | SVG из Heroicons / Lucide |
| `transform: scale()` на hover в grid | `translateY(-Npx)` или цвет/border |
| Залить большую площадь оранжевым | Оранжевый — только акцент (spark, eyebrow, hover) |
| `font-weight: 700` для цифр статистики | `font-weight: 300` (Light) — фирменно |
| Курсив `font-style: italic` для `<em>` | `font-style: normal` + оранжевый градиент через background-clip |
| Hero без фонового изображения | Hero ВСЕГДА имеет 3D PNG или градиентную текстуру |

---

## 14. ПРИНЦИПЫ КОМПОЗИЦИИ

1. **Чёрный фон — норма.** Контент «всплывает» из темноты через стекло.
2. **Оранжевый — точечный.** Только акценты: spark, eyebrow num, hover state, оранжевый em-градиент.
3. **Свет всегда тёплый.** Никаких холодных hue — palette фиксирована на warm orange (без золота).
4. **Цифры — Light (300).** Никогда жирные — это убивает премиальность.
5. **Liquid Glass — единый паттерн.** Любой контейнер карточка → бери базу из §3.
6. **Spark на hover — ВСЕГДА на интерактивных карточках.** Это фирменный признак.
7. **Большие межбуквенные интервалы.** Eyebrow letter-spacing 0.18em UPPERCASE — ритм страницы.
8. **H2 line-height 0.9.** Заголовки плотные, не расхлябанные.

---

## 15. КОГДА ЧТО ИСПОЛЬЗОВАТЬ

| Задача | Что брать |
|---|---|
| Карточка-фичи / преимущество | §3 Liquid Glass card + §4 Spark |
| Сетка 6 ячеек / преимуществ | §5 Glass Grid + spark + nth-child borders |
| Заголовок секции | §6 Section Eyebrow + §2 H2 orange-em |
| Manifesto / провокационный заголовок | §7 Strike pattern |
| Hero / first screen | §8 Hero full-bleed |
| Презентация (слайды Keynote/Figma) | §1 палитра + §2 типографика + §3 glass + §6 eyebrow |
| 3D-визуал (PNG для hero) | §12 Higgsfield промпт |
| Stats блок | §2 цифры Light 300 + §3 glass background |

---

## 16. ГОТОВЫЙ STAND-ALONE TEMPLATE

Минимальная страница со всеми фирменными элементами:

```html
<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Hugency Style Demo</title>
<style>
:root {
  --bg-0: #000000; --bg-1: #050505; --bg-2: #0a0a0a;
  --accent-1: #FF7A3D; --accent-3: #E55A1F; --accent-5: #B84415;
  --ember-1: #FF9A55; --ember-3: #FF7A3D; --ember-5: #E55A1F;
  --text: #f4f4f0; --text-soft: #d8d8d2; --text-dim: #bcbcb4; --text-mute: #a4a49c;
  --glass-bg: rgba(255,255,255,0.03);
  --glass-bg-hover: rgba(255,255,255,0.05);
  --glass-border: rgba(255,255,255,0.12);
  --spark-color: var(--accent-1);
  --spark-hot: #FFD2A0;
}
* { margin: 0; padding: 0; box-sizing: border-box; }
body {
  min-height: 100vh;
  background: radial-gradient(ellipse 80% 60% at 50% 50%, #1a1a1c 0%, #0a0a0b 60%, #050505 100%);
  font-family: "Vela Sans", "SF Pro Display", -apple-system, BlinkMacSystemFont, "Inter", sans-serif;
  color: var(--text);
  -webkit-font-smoothing: antialiased;
}
.wrap { max-width: 1080px; margin: 0 auto; padding: 80px 48px; }

/* Section eyebrow */
.section-eyebrow { display: flex; align-items: baseline; gap: 16px; margin-bottom: 18px; }
.section-eyebrow .num {
  font-weight: 400; color: var(--ember-3);
  font-size: clamp(40px, 5vw, 64px); letter-spacing: -0.04em;
}
.section-eyebrow .label {
  font-weight: 500; color: var(--text-soft);
  font-size: 13px; letter-spacing: 0.18em; text-transform: uppercase;
}

/* H2 */
h2 {
  font-size: clamp(36px, 5.8vw, 64px); font-weight: 500;
  letter-spacing: -0.035em; line-height: 0.9;
  margin-bottom: 28px; max-width: 920px;
}
h2 em {
  font-style: normal; font-weight: 500;
  background: linear-gradient(135deg, var(--ember-1), var(--ember-3), var(--ember-5));
  -webkit-background-clip: text; background-clip: text;
  -webkit-text-fill-color: transparent; color: transparent;
}

/* Glass grid */
.glass-grid {
  display: grid; grid-template-columns: repeat(3, 1fr); gap: 0;
  border-radius: 22px; overflow: hidden;
  background: var(--glass-bg);
  backdrop-filter: blur(28px) saturate(140%);
  -webkit-backdrop-filter: blur(28px) saturate(140%);
  border: 1px solid var(--glass-border);
  margin-top: 56px;
}
.glass-cell {
  position: relative; padding: 22px 30px 24px;
  border-right: 1px solid rgba(255,255,255,0.10);
  border-bottom: 1px solid rgba(255,255,255,0.10);
  overflow: hidden;
  transition: background 0.4s ease;
}
.glass-cell:hover { background: rgba(255,255,255,0.025); }
.glass-grid .glass-cell:nth-child(3n) { border-right: none; }
.glass-grid .glass-cell:nth-last-child(-n+3) { border-bottom: none; }

/* SPARK на hover */
.glass-cell::after {
  content: ''; position: absolute; inset: 0;
  padding: 1px; border-radius: inherit;
  background: conic-gradient(
    from 0deg,
    transparent 0deg, transparent 38deg,
    var(--spark-color) 52deg, var(--spark-hot) 65deg, var(--spark-color) 80deg,
    transparent 96deg, transparent 218deg,
    var(--spark-color) 232deg, var(--spark-hot) 245deg, var(--spark-color) 260deg,
    transparent 276deg, transparent 360deg
  );
  -webkit-mask: linear-gradient(#000 0 0) content-box, linear-gradient(#000 0 0);
          mask: linear-gradient(#000 0 0) content-box, linear-gradient(#000 0 0);
  -webkit-mask-composite: xor; mask-composite: exclude;
  pointer-events: none; opacity: 0; transition: opacity 0.5s ease;
  z-index: 1;
}
.glass-cell:hover::after { opacity: 1; }

.cell-num {
  position: relative; z-index: 2;
  font-size: clamp(30px, 2.6vw, 42px); font-weight: 700;
  color: rgba(255,255,255,0.72); margin-bottom: 14px;
  letter-spacing: -0.04em;
  transition: color 0.4s ease, transform 0.4s cubic-bezier(.2,.7,.2,1);
  transform-origin: left center;
}
.glass-cell:hover .cell-num { color: var(--accent-3); transform: scale(1.12); }
.cell-title {
  position: relative; z-index: 2;
  font-size: 18px; font-weight: 600; color: var(--text);
  margin-bottom: 8px; line-height: 1.35;
}
.cell-desc {
  position: relative; z-index: 2;
  font-size: 14px; line-height: 1.55; color: var(--text-mute);
}

@media (max-width: 900px) {
  .glass-grid { grid-template-columns: repeat(2, 1fr); }
}
@media (max-width: 600px) {
  .glass-grid { grid-template-columns: 1fr; }
}
</style>
</head>
<body>
  <main class="wrap">
    <div class="section-eyebrow"><span class="num">05</span><span class="label">H-Framework</span></div>
    <h2>Система, которая превращает контент в <em>прибыль</em></h2>

    <div class="glass-grid">
      <div class="glass-cell">
        <div class="cell-num">1</div>
        <div class="cell-title">Фокус на выручке</div>
        <div class="cell-desc">Не интересны просмотры — фокус на заявках, выручке и окупаемости.</div>
      </div>
      <div class="glass-cell">
        <div class="cell-num">2</div>
        <div class="cell-title">AI как часть сервиса</div>
        <div class="cell-desc">Реальные инструменты — не просто ускоряют выпуск контента.</div>
      </div>
      <div class="glass-cell">
        <div class="cell-num">3</div>
        <div class="cell-title">Постоянное обучение</div>
        <div class="cell-desc">Каждую неделю изучаем новые алгоритмы платформ и AI-модели.</div>
      </div>
      <div class="glass-cell">
        <div class="cell-num">4</div>
        <div class="cell-title">Работаем в долгую</div>
        <div class="cell-desc">Средний срок — 7 месяцев. За 1–2 не построить маркетинг-машину.</div>
      </div>
      <div class="glass-cell">
        <div class="cell-num">5</div>
        <div class="cell-title">Мульти-канальность</div>
        <div class="cell-desc">Reels, TikTok, YouTube — у одного подрядчика.</div>
      </div>
      <div class="glass-cell">
        <div class="cell-num">6</div>
        <div class="cell-title">Партнёрство</div>
        <div class="cell-desc">С 3-го месяца — формат с процентом или оплатой за заявку.</div>
      </div>
    </div>
  </main>
</body>
</html>
```

Открой в браузере → должно быть видно: тёмный фон, orange-em в заголовке, 6 склеенных стеклянных ячеек, и при наведении на каждую — 2 оранжевые искры в углах + scale цифры в оранжевый.

---

## ИСПОЛЬЗОВАНИЕ

При запросе пользователя в стиле Hugency:

1. **Применяй §1 палитру и §2 типографику** на корень проекта
2. **Все карточки** — через §3 Liquid Glass + §4 Spark
3. **Заголовки секций** — через §6 Eyebrow + §2 H2 orange-em
4. **Hero** — через §8 Full-bleed
5. **Презентации** — переиспользуй те же токены, только в Figma/Keynote
6. **3D-ассеты** — генерируй через §12 Higgsfield промпт

При генерации `.html` проекта — копируй §16 как стартовый скелет, дальше дополняй контентом.

---

## РОДСТВЕННЫЕ ФАЙЛЫ (когда работаешь с самим HUGENCY)

- `/Users/rama/Desktop/CLAUDE/HUGENCY/HUGENCY_DNA_v2.md` — полное ДНК бренда (месседжи, ICP, кейсы, ToV)
- `/Users/rama/Desktop/CLAUDE/HUGENCY/LANDING_CNG_LAB.html` — live RU-лендинг (источник всех паттернов)
- `/Users/rama/Desktop/CLAUDE/HUGENCY/LANDING_CNG_LAB_EN.html` — EN-зеркало
- `/Users/rama/Desktop/CLAUDE/HUGENCY/fonts/VelaSans-GX.ttf` — variable font файл

---

*Версия 1.0 · Источник: live `LANDING_CNG_LAB.html` (май 2026)*
