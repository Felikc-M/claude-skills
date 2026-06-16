---
name: trely-design-2
description: Production-визуал shipping.trely.io. Веб-дизайн-система Trely как она реально живёт на сайте — cream фон + gold акценты + deep green секции, Inter Tight Medium 500, конкретные паттерны (поисковая карточка с бордерами, hero stats компактные, gold-circle 6-шаговый процесс, FAQ, compare-table, traveler CTA с painterly иллюстрацией). Используй когда пользователь упоминает — "стиль shipping.trely.io", "как на trely shipping", "веб-стиль Trely", "geo-страница Trely", "лендинг Trely shipping", "продуктовая страница trely.io", "trely web". Отличие от skill trely-design — там брендбук+pitch deck (Bold 700, slide-first), здесь production-web (Medium 500, web-first, готовые конверсионные секции).
---

# TRELY DESIGN 2 — Production веб-визуал shipping.trely.io

> Источник: реальный production-код shipping.trely.io (извлечён через DOM/CSS-инспекцию) + дополнительные конверсионные блоки в том же стиле. Базовый брендбук — см. соседний скилл `trely-design`.

## Когда использовать ЭТО, а не trely-design

| Задача | Скилл |
|---|---|
| Лендинг / геостраница / маршрутная страница shipping.trely.io | **trely-design-2** ← |
| Конверсионная страница продукта | **trely-design-2** ← |
| Слайд для презентации, обложка, ад-креатив | trely-design |
| Печатная продукция, брендбук-материалы | trely-design |
| Сомневаешься | trely-design-2 для веба, trely-design для всего остального |

## TL;DR — что отличает trely-design-2

1. **Шрифт заголовков — Inter Tight 500 (Medium), не 700 Bold**. Tracking −0.01em, не −0.02em. На веб-сайте Trely заголовки мягче чем в pitch deck.
2. **H1 — 56px ровно**, не clamp. H2 — 40px ровно. Размеры из production.
3. **Поисковая карточка** — фирменный паттерн с бордерными полями, золотой кнопкой "Найти" 60px и тёмно-зелёным круглым swap.
4. **Hero stats** — компактная белая плашка с золотыми цифрами 30px и тонкими divider'ами.
5. **Steps процесса** — gold-circle 48px numbers, белые карточки с soft shadow (а не cream без shadow как в pitch deck).
6. **Compare table** — фирменный паттерн "Trely vs DHL/Почта/Карго" с deep-green колонкой Trely и золотой иконкой/цифрами.
7. **Traveler CTA** — deep-green блок с painterly иллюстрацией справа и сеткой gold-perks 2×2.
8. **FAQ** — pill `+` cream-кружок, rotate(90) на hover.

## Сразу — токены (вставь в начало проекта)

```css
:root{
  --tr-green:#273C3F;       /* Deep Travel Green — dark sections */
  --tr-green-card:#1A2F2F;  /* чуть светлее для карточек внутри dark sections */
  --tr-gold:#C6A064;        /* Explorer Gold — все акценты */
  --tr-gold-grad-1:#D4B57A; /* для gold-gradient кнопок */
  --tr-gold-grad-2:#A8854F;
  --tr-cream:#F7F6F4;       /* основной фон сайта */
  --tr-cream-sub:#E8E2D2;   /* декоративные арки/круги */
  --tr-white:#FFFFFF;
  --tr-ink:#0F1014;
  --tr-tag:#EDE4D1;         /* warm-tag, inline-пилюли */
  --tr-gray-60:#6B6F71;
  --tr-gray-40:#A0A4A6;
  --tr-divider:#E5E2DC;     /* границы полей, разделители */

  --r-sm:8px; --r-md:16px; --r-lg:24px; --r-xl:32px; --r-pill:999px;

  --sh-soft:0 4px 24px rgba(39,60,63,.06);
  --sh-medium:0 8px 32px rgba(39,60,63,.10);
  --sh-btn:0 2px 8px rgba(15,16,20,.10);

  --ff:'Inter Tight',-apple-system,system-ui,sans-serif;
}
body{font-family:var(--ff);background:var(--tr-cream);color:var(--tr-ink);letter-spacing:-0.01em}
h1{font-size:56px;font-weight:500;line-height:1.14;letter-spacing:-0.01em}
h2{font-size:40px;font-weight:500;line-height:1.15;letter-spacing:-0.01em}
h3{font-size:20px;font-weight:500;letter-spacing:-0.01em}
```

**Запомни критичное:** на shipping.trely.io все заголовки — **Medium 500**, не Bold. Это самая частая ошибка при переносе из брендбука/pitch deck.

## Анатомия страницы (15 блоков под полный конверсионный лендинг)

Порядок проверен на shipping.trely.io + расширен под geo/конверсию:

1. **Header sticky cream** — логотип "Trely" текстом 28/600, nav-links с gold-symbol "+", lang-pill с RU-флагом, profile-pill, chat-btn с coral бейджем
2. **Hero** — H1, лид-параграф 17-20px gray, hero-stats компактная плашка (4 цифры gold), search-card с бордерами, иллюстрация ниже
3. **Trust strip deep-green** — лента из 4 пунктов (эскроу/верификация/24·7/страховка) с gold-иконками 44px
4. **Calculator** — left text + right white card-widget с золотой ценой 42px и delta-пилюлей
5. **Compare table** — Trely vs DHL/FedEx/Почта/Карго, deep-green header колонки Trely с золотой точкой
6. **How it works** — 3×2 grid из шести cards с gold-circle 48px numbers
7. **Popular routes** — горизонтальный snap-carousel, карточки 300×400 с белым label-блоком внизу
8. **Why us** — 3 cards с фоном-иллюстрацией внутри (payment/support/users)
9. **Allowed / Forbidden** — две white-cards с cat-pill "Можно/Запрещено", иконки списка gold/cream-sub
10. **Safety** — 2×3 grid cards с иконкой 56px в cream-квадрате
11. **Big stats deep-green** — 4 цифры 72px gold с подписями белым
12. **Cases** — 3 white-cards с маршрутом, товаром, экономией
13. **Testimonials deep-green** — horizontal snap-carousel с большими карточками 240px фото + цитата
14. **Traveler CTA deep-green** — 1.2fr text + 1fr с painterly иллюстрацией справа и gold-perks 2×2
15. **Press logos** → **App download** → **FAQ** → **Final CTA** → **Footer 5-col**

Готовый шаблон со всеми 15 блоками — `templates/shipping-landing-full.html`. Открывай его и копируй секции.

## Ключевые паттерны (вставляй как есть)

### Header (cream sticky)

```html
<header class="site">
  <div class="container nav">
    <div class="logo">Trely</div>
    <nav class="nav-links">
      <a href="#" class="muted-gold">Отправить посылку <span class="plus">+</span></a>
      <a href="#" class="muted-gold">Стать доставщиком <span class="plus">+</span></a>
      <a href="#">Объявления</a>
      <a href="#">Отклики</a>
    </nav>
    <div class="nav-right">
      <div class="lang-pill"><span class="flag"></span>RU ▾</div>
      <div class="profile-pill">Профиль <span class="avatar">●</span> ▾</div>
      <button class="chat-btn"><svg>...</svg><span class="badge">2</span></button>
    </div>
  </div>
</header>
```
```css
header.site{position:sticky;top:0;z-index:50;background:var(--tr-cream)}
.nav{display:flex;align-items:center;gap:32px;height:72px}
.logo{font-size:28px;font-weight:600;letter-spacing:-0.02em}
.nav-links{display:flex;gap:28px;margin-left:24px}
.nav-links a{font-size:15px;color:#1a1a1a;font-weight:500;display:flex;align-items:center;gap:6px}
.nav-links a.muted-gold{color:var(--tr-gold)}
.nav-links .plus{display:inline-flex;width:20px;height:20px;border-radius:50%;background:rgba(198,160,100,.10);color:var(--tr-gold);align-items:center;justify-content:center;font-size:14px}
.lang-pill{display:flex;align-items:center;gap:8px;background:#fff;border:1px solid rgba(0,0,0,.06);border-radius:12px;padding:6px 10px;font-size:14px;font-weight:500}
.chat-btn{position:relative;width:40px;height:40px;border-radius:50%;background:#F4F2EE}
.chat-btn .badge{position:absolute;top:-2px;right:-2px;background:#FF5F4D;color:#fff;font-size:11px;border-radius:50%;width:18px;height:18px;display:flex;align-items:center;justify-content:center;font-weight:600}
```

### Hero — search card (фирменный, с бордерами и золотой кнопкой)

```html
<div class="search-card">
  <div class="search-field"><input placeholder="Откуда" /></div>
  <button class="swap-btn"><svg stroke="#fff">⇄</svg></button>
  <div class="search-field"><input placeholder="Куда" /></div>
  <div class="search-field date-field">
    <input placeholder="Дата поездки" />
    <svg stroke="#A0A4A6">📅</svg>
  </div>
  <button class="btn-primary">Найти</button>
</div>
```
```css
.search-card{background:#fff;border-radius:32px;box-shadow:var(--sh-medium);padding:18px;display:grid;grid-template-columns:1fr auto 1fr 1fr auto;gap:14px;align-items:center;max-width:1180px;margin:38px auto 0}
.search-field{padding:18px 22px;border-radius:14px;border:1px solid var(--tr-divider);display:flex;align-items:center}
.search-field input{width:100%;border:none;outline:none;font-size:15px;font-family:inherit;background:transparent}
.search-field input::placeholder{color:var(--tr-gray-60)}
.swap-btn{width:34px;height:34px;border-radius:50%;background:var(--tr-green);color:#fff;display:flex;align-items:center;justify-content:center}
.search-card .btn-primary{background:var(--tr-gold);color:#fff;border-radius:14px;padding:0 50px;height:60px;font-weight:600;font-size:16px;border:none}
```

### Hero stats (компактная плашка с золотыми цифрами)

```html
<div class="hero-stats">
  <div class="stat"><div class="num">700<small>+</small></div><div class="lbl">направлений по миру</div></div>
  <div class="stat"><div class="num">12 500<small>+</small></div><div class="lbl">проверенных пользователей</div></div>
  <div class="stat"><div class="num">от 2<small> дн.</small></div><div class="lbl">средний срок доставки</div></div>
  <div class="stat"><div class="num">−64<small>%</small></div><div class="lbl">экономия vs курьеры</div></div>
</div>
```
```css
.hero-stats{margin:32px auto 0;display:grid;grid-template-columns:repeat(4,1fr);gap:0;max-width:880px;background:#fff;border-radius:32px;padding:20px 12px;box-shadow:var(--sh-soft)}
.hero-stats .stat{text-align:center;padding:6px 16px;border-right:1px solid var(--tr-divider)}
.hero-stats .stat:last-child{border-right:none}
.hero-stats .stat .num{font-size:30px;font-weight:700;color:var(--tr-gold);line-height:1;letter-spacing:-0.02em}
.hero-stats .stat .num small{font-size:18px;font-weight:600}
.hero-stats .stat .lbl{margin-top:8px;font-size:12px;color:var(--tr-gray-60)}
```

### How-it-works (gold-circle 48px steps)

```css
.hw-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:20px}
.hw-card{background:#fff;border-radius:32px;padding:36px 30px;box-shadow:var(--sh-soft)}
.hw-num{display:inline-flex;align-items:center;justify-content:center;width:48px;height:48px;border-radius:50%;background:var(--tr-gold);color:var(--tr-ink);font-weight:700;font-size:20px;margin-bottom:22px}
.hw-card h3{font-size:20px;font-weight:500;margin-bottom:10px}
.hw-card p{font-size:15px;color:var(--tr-gray-60);line-height:1.55}
.hw-card .meta{margin-top:18px;font-size:12px;color:var(--tr-gold);font-weight:600;text-transform:uppercase;letter-spacing:0.08em;display:flex;align-items:center;gap:8px}
.hw-card .meta::before{content:"";width:18px;height:1px;background:var(--tr-gold)}
```

### Compare table (Trely vs альтернативы)

```css
.compare-wrap{background:#fff;border-radius:32px;overflow:hidden;box-shadow:var(--sh-soft)}
.compare{width:100%;border-collapse:collapse;font-size:15px}
.compare th,.compare td{padding:20px 22px;text-align:center;border-bottom:1px solid var(--tr-divider)}
.compare th{background:var(--tr-cream);font-weight:500;font-size:14px}
.compare th:first-child,.compare td:first-child{text-align:left}
.compare th.col-trely{background:var(--tr-green);color:#fff;font-weight:600}
.compare th.col-trely::before{content:"";display:inline-block;width:14px;height:14px;background:var(--tr-gold);border-radius:50%;margin-right:8px;vertical-align:middle}
.compare .col-trely{background:rgba(198,160,100,.08)}
.compare .col-trely b{color:var(--tr-gold)}
.check{display:inline-flex;width:24px;height:24px;border-radius:50%;background:var(--tr-gold);color:#fff;align-items:center;justify-content:center;font-weight:700}
.cross{display:inline-flex;width:24px;height:24px;border-radius:50%;background:var(--tr-cream);color:var(--tr-gray-40);align-items:center;justify-content:center;font-weight:700}
.partial{color:var(--tr-gray-60);font-style:italic;font-size:13px}
```

### Trust strip (deep green с gold-иконками 44px)

```css
.trust-strip{background:var(--tr-green);color:var(--tr-cream);padding:32px 0;border-radius:32px 32px 0 0}
.trust-strip .row{display:grid;grid-template-columns:repeat(4,1fr);gap:24px}
.trust-item{display:flex;align-items:center;gap:14px;font-size:14px;color:#cfd1d1}
.trust-item .ico{width:44px;height:44px;border-radius:16px;background:rgba(198,160,100,.15);color:var(--tr-gold);display:flex;align-items:center;justify-content:center}
.trust-item b{display:block;color:#fff;font-weight:600;font-size:14px}
.trust-item span{color:rgba(255,255,255,.55);font-size:12px}
```

### Big stats (deep green hero-блок)

```css
.big-stats{background:var(--tr-green);color:#fff;padding:96px 0;border-radius:32px;position:relative;overflow:hidden}
.big-stats::before,.big-stats::after{content:"";position:absolute;border-radius:50%;background:rgba(198,160,100,.06)}
.big-stats::before{top:-200px;left:-150px;width:500px;height:500px}
.big-stats::after{bottom:-200px;right:-150px;width:500px;height:500px}
.big-stats .stat .num{font-size:72px;font-weight:700;color:var(--tr-gold);letter-spacing:-0.03em;line-height:1}
.big-stats .stat .lbl{margin-top:16px;font-size:15px;color:rgba(255,255,255,.7)}
```

### Traveler CTA (deep green с painterly иллюстрацией)

```css
.traveler{background:var(--tr-green);border-radius:32px;padding:72px 64px;color:var(--tr-cream);display:grid;grid-template-columns:1.2fr 1fr;gap:48px;align-items:center;position:relative;overflow:hidden}
.traveler::before{content:"";position:absolute;top:-150px;right:-100px;width:520px;height:520px;border-radius:50%;background:rgba(198,160,100,.08)}
.traveler-illust{position:absolute;right:-40px;top:50%;transform:translateY(-50%);width:340px}
.traveler .perk{background:rgba(255,255,255,.05);border:1px solid rgba(198,160,100,.18);border-radius:16px;padding:20px}
.traveler .perk .v{font-size:32px;font-weight:700;color:var(--tr-gold)}
```

### FAQ accordion

```css
.faq-item{border-bottom:1px solid var(--tr-divider);padding:26px 4px;cursor:pointer}
.faq-item .q{font-size:18px;font-weight:500}
.faq-plus{width:40px;height:40px;border-radius:50%;background:var(--tr-cream);color:var(--tr-gold);display:flex;align-items:center;justify-content:center;font-size:22px;transition:transform .2s}
.faq-item:hover .faq-plus{transform:rotate(90deg);background:var(--tr-tag)}
```

## Иллюстрации (painterly из брендбука)

| Где | Файл |
|---|---|
| Hero shipping (если painterly) | `assets/illustrations/characters/03-shipping-boy-luggage.png` |
| Hero shipping (если оригинальный сайт) | `assets/hero-imgx2-new.webp` |
| Traveler CTA | `assets/illustrations/characters/06-travelclub-boy-bali.png` |
| App download | `assets/illustrations/characters/02-mascot-main-green.png` |
| Coupon/Avia блок | `assets/illustrations/objects/02-plane-green-gold.png` |
| Объект-иконка коробки | `assets/illustrations/objects/01-box-green-stars.png` |

## Тоновый код (важно для копирайта в этих блоках)

- Заголовки декларативные, без вопросов: «Надёжная доставка руками реальных людей»
- Лид-параграф объясняет «что и зачем» одним предложением 17-20px gray
- Цифры — **золотом**, всегда с единицей измерения («от 2 дн.», «−64%», «12 500+»)
- Каждый раздел открывается eyebrow caps: `Процесс / Сравнение / Истории / Безопасность` — 13px gold uppercase letter-spacing 0.14em
- Кнопки: основная «Найти» / «Разместить заявку» — gold-fill 60px. Вторичная — outline near-black pill.
- В тёмных секциях вторичная — outline white

## Чек-лист "это в стиле shipping.trely.io?"

- [ ] Фон страницы `#F7F6F4` (cream), не белый
- [ ] H1/H2 — Inter Tight **Medium 500**, не Bold. Tracking −0.01em
- [ ] Поисковая карточка — поля в бордерах, swap deep-green круг, кнопка gold 60px (не near-black)
- [ ] Hero stats — белая плашка с золотыми цифрами 30px и divider'ами
- [ ] Process steps — gold-circle 48px numbers, белые карточки
- [ ] Compare-таблица — колонка Trely с deep-green header и золотой точкой
- [ ] Trust strip / Big stats / Testimonials / Traveler — deep green с золотыми акцентами
- [ ] Eyebrow caps gold над каждой секцией
- [ ] Painterly иллюстрации в hero / traveler / app блоках (не stock и не эмодзи)
- [ ] FAQ — pill `+` cream-кружок с rotate(90) на hover
- [ ] Footer — 5 колонок (Сервис / Направления / Помощь / Компания + brand), не одна сплошная строка

## Полный шаблон

`templates/shipping-landing-full.html` — готовый рабочий лендинг со всеми 15 блоками, все CSS inline, использует assets из этой папки. Открой его, скопируй секции которые нужны, переименуй классы если переносишь в свой стэк.

---

**Версия:** 1.0 — извлечено из production shipping.trely.io 06.2026 + расширение конверсионными блоками (calculator, compare, allowed/forbidden, safety, cases, traveler CTA, press, app, expanded FAQ).
