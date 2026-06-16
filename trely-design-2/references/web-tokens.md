# Web tokens — точные значения из shipping.trely.io

Извлечены через DOM/CSS-инспекцию production-сайта 06.2026 + расширение под конверсионные блоки.

## Палитра (HEX)

```
#FFFFFF  white         — search-card, why-cards, cases, FAQ, footer brand row
#F7F6F4  cream         — основной фон body, footer, app block
#E8E2D2  cream-sub     — декоративные арки/круги в hero, calc, traveler, final-cta
#EDE4D1  warm-tag      — cat-pills "Можно отправлять", inline-теги
#E5E2DC  divider       — border полей search-card, разделители hero-stats и таблиц
#F4F2EE  chat-bg       — фон круглой chat-btn в хедере, swap-btn (старый вариант)
#C6A064  gold          — все цифры в плашках, иконки, кнопка "Найти", arrows, dot в col-trely header
#D4B57A→#A8854F  gold-gradient — кнопка "Войти" / опциональные telegram-CTA
#273C3F  deep-green    — trust-strip, big-stats, testimonials, traveler, swap-btn кружок
#1A2F2F  green-card    — карточки внутри testimonials (чуть светлее основного dark BG)
#0F1014  ink           — основной текст, обычные кнопки primary
#6B6F71  gray-60       — лид, подписи под цифрами, плейсхолдеры, описания cards
#A0A4A6  gray-40       — disabled, иконка календаря в date-field
#FF5F4D  coral         — ТОЛЬКО для бейджа уведомлений в chat-btn (chat badge "2")
```

**Запрещено:** синий, зелёный (кроме deep-green), оранжевый, фиолетовый в UI. Coral допустим **только** в chat-badge.

## Типографика (точные размеры из production)

| Уровень | Размер | Вес | LH | Tracking | Цвет |
|---|---|---|---|---|---|
| H1 hero | **56px** | **500** | 1.14 | −0.01em | #0F1014 |
| H2 секции | **40px** | **500** | 1.15 | −0.01em | #0F1014 |
| H3 cards | 20px | 500 (бывает 600 в FAQ/case-item) | 1.3 | −0.01em | #0F1014 |
| Hero lead | 20px | 400 | 1.5 | — | #6B6F71 |
| Section sub | 16-17px | 400 | 1.55 | — | #6B6F71 |
| Body | 15px | 400 | 1.55 | — | #1a1a1a |
| Eyebrow caps | 13px | 600 | 1 | +0.14em | #C6A064 (UPPERCASE) |
| Stat num hero | 30px | 700 | 1 | −0.02em | #C6A064 |
| Stat num big | 72px | 700 | 1 | −0.03em | #C6A064 |
| Step number circle | 20px | 700 | 1 | — | #0F1014 (на gold-фоне) |
| Caption | 12-13px | 400-500 | 1.4 | — | #6B6F71 |

**Глобальное правило:** `body { letter-spacing: -0.01em }` — на всём документе.

**Шрифт-стак:**
```css
font-family:'Inter Tight',-apple-system,system-ui,sans-serif;
```

Включи Google Fonts:
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter+Tight:wght@300;400;500;600;700&display=swap" rel="stylesheet">
```

## Радиусы

| Где | Значение |
|---|---|
| search-field, calc-field, date-field | **14px** |
| btn "Найти" в search-card | **14px** |
| input chat-btn, lang-pill | 12px |
| card обычная (cases, safety, hw-card, ag-card) | **32px** (xl) |
| hero-stats, search-card, big-stats, traveler, app, final-cta wrapper | **32px** (xl) |
| compare-wrap, footer | 32px (xl) |
| route-card | 32px |
| label на route-card | 16px (md) |
| swap-btn | 50% (круг) |
| chat-btn, arrow-btn | 50% (круг) |
| pills (eyebrow, status, lang-pill) | 999px (pill) |

## Тени

| Тип | Значение |
|---|---|
| Карточка soft | `0 4px 24px rgba(39,60,63,.06)` |
| Карточка hover/medium | `0 8px 32px rgba(39,60,63,.10)` |
| Кнопка primary | `0 2px 8px rgba(15,16,20,.10)` |
| Кнопка gold-gradient | `0 2px 12px rgba(168,133,79,.25)` |
| Mock-card в why-payment | `0 12px 30px rgba(39,60,63,.12)` |

Никогда не делай тени более 32px blur — на cream они становятся "грязными".

## Сетка/контейнеры

```css
.container{max-width:1320px;margin:0 auto;padding:0 64px}
@media(max-width:900px){.container{padding:0 24px}}
```

- Hero: высота 72px header, padding-top hero ~48px
- Section padding-vertical: 96px (desktop), 64px (mobile)
- Gap между блоками внутри grid: 18-24px
- Hero-stats max-width: 880px (отдельно, уже container)
- Search-card max-width: 1180px
- Testimonials track padding: 0 64px с margin: 0 -64px (для overflow snap)

## Кнопки (точные значения)

### Primary (near-black pill) — обычная CTA в секциях
```css
.btn-primary{background:#0F1014;color:#fff;border-radius:999px;padding:14px 28px;font-weight:600;font-size:15px;box-shadow:0 2px 8px rgba(15,16,20,.10)}
```

### Primary "Найти" в search-card — ИСКЛЮЧЕНИЕ, gold не pill
```css
.search-card .btn-primary{background:#C6A064;color:#fff;border-radius:14px;padding:0 50px;height:60px;font-weight:600;font-size:16px;box-shadow:none}
```

### Secondary outline
```css
.btn-secondary{background:transparent;color:#0F1014;border:1.5px solid #0F1014;border-radius:999px;padding:12px 26px;font-weight:500;font-size:15px}
```

### Gold gradient (для header "Войти" / Telegram-CTA)
```css
.btn-gold{background:linear-gradient(90deg,#D4B57A 0%,#A8854F 100%);color:#fff;border-radius:999px;padding:14px 28px;font-weight:600;font-size:15px}
```

### Light (на тёмных секциях)
```css
.btn-light{background:#fff;color:#0F1014;border-radius:999px;padding:14px 28px;font-weight:600;font-size:15px}
```

### Ghost dark (на тёмных секциях)
```css
.btn-ghost-dark{background:transparent;color:#fff;border:1.5px solid rgba(255,255,255,.4);border-radius:999px;padding:12px 26px}
```

## Что НЕ делать (типичные ошибки переноса)

- ❌ Использовать H1/H2 **Bold 700** — это слайды/деки, а на сайте **Medium 500**
- ❌ Tracking −0.02em на H1/H2 — на сайте −0.01em (более мягко)
- ❌ Делать кнопку "Найти" в форме поиска тёмной pill — она **gold** прямоугольная с радиусом 14px
- ❌ Заворачивать "Откуда/Куда" поля без бордера — на сайте у каждого поля свой border
- ❌ Менять swap-btn на cream-кружок — он **deep-green** круг с белыми стрелками
- ❌ Использовать coral/красный/зелёный в UI любых других мест кроме chat-badge
- ❌ Кнопка primary без shadow — у неё всегда лёгкая `0 2px 8px rgba(15,16,20,.10)`
