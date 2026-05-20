# TRELY — Компонентная библиотека

Готовые компоненты с CSS. Скопируй и адаптируй.

---

## Tokens (вставь в начало любого проекта)

```css
:root {
  /* Colors */
  --tr-green: #273C3F;
  --tr-gold:  #C6A064;
  --tr-cream: #F7F6F4;
  --tr-white: #FFFFFF;
  --tr-ink:   #0F1014;
  --tr-tag:   #EDE4D1;
  --tr-gray-60: #6B6F71;
  --tr-gray-40: #A0A4A6;
  --tr-green-card: #1A2F2F;
  --tr-cream-sub: #E8E2D2;

  /* Radii */
  --r-sm: 8px;
  --r-md: 16px;
  --r-lg: 24px;
  --r-xl: 32px;
  --r-pill: 999px;

  /* Shadows */
  --sh-soft: 0 4px 24px rgba(39, 60, 63, 0.06);
  --sh-medium: 0 8px 32px rgba(39, 60, 63, 0.10);
  --sh-btn: 0 2px 8px rgba(15, 16, 20, 0.10);

  /* Type */
  --ff: 'Inter Tight', -apple-system, system-ui, sans-serif;
}

body {
  font-family: var(--ff);
  background: var(--tr-cream);
  color: var(--tr-ink);
  letter-spacing: -0.01em;
}
```

---

## 1. Primary button (CTA)

```html
<button class="btn-primary">Отправить с Trely</button>
```
```css
.btn-primary {
  background: var(--tr-ink);
  color: var(--tr-white);
  font-family: var(--ff);
  font-weight: 600;
  font-size: 16px;
  padding: 14px 28px;
  border-radius: var(--r-pill);
  border: none;
  cursor: pointer;
  box-shadow: var(--sh-btn);
  transition: transform .15s;
}
.btn-primary:hover { transform: translateY(-1px); }
```

### Gold variant (для дополнительной важности)
```css
.btn-gold {
  background: var(--tr-gold);
  color: var(--tr-ink);
  /* остальное как .btn-primary */
}
```

---

## 2. Secondary button (outline)

```html
<button class="btn-secondary">Подробнее</button>
```
```css
.btn-secondary {
  background: transparent;
  color: var(--tr-ink);
  border: 1.5px solid var(--tr-ink);
  font-weight: 500;
  font-size: 16px;
  padding: 12px 26px;
  border-radius: var(--r-pill);
  cursor: pointer;
}
```

---

## 3. Card (на cream фоне)

```html
<div class="card">
  <h3>Заголовок карточки</h3>
  <p>Описание Regular серым</p>
</div>
```
```css
.card {
  background: var(--tr-white);
  border-radius: var(--r-lg);
  padding: 32px;
  box-shadow: var(--sh-soft);
}
.card h3 { font-size: 22px; font-weight: 600; margin: 0 0 8px; }
.card p { font-size: 16px; color: var(--tr-gray-60); margin: 0; }
```

### Dark card (на тёмно-зелёном фоне)
```css
.card-dark {
  background: var(--tr-green-card);
  color: var(--tr-white);
  border-radius: var(--r-lg);
  padding: 32px;
}
```

---

## 4. Stat card (метрика с золотой цифрой)

```html
<div class="stat-card">
  <div class="stat-icon">👤</div>
  <div class="stat-num">55 000</div>
  <div class="stat-label">пользователей по всему миру</div>
</div>
```
```css
.stat-card {
  background: var(--tr-white);
  border-radius: var(--r-xl);
  padding: 48px 32px;
  text-align: center;
  box-shadow: var(--sh-soft);
}
.stat-icon {
  width: 56px; height: 56px;
  border-radius: 50%;
  background: var(--tr-cream);
  display: inline-flex; align-items: center; justify-content: center;
  margin-bottom: 24px;
  font-size: 24px;
}
.stat-num {
  font-size: clamp(56px, 8vw, 96px);
  font-weight: 700;
  color: var(--tr-gold);
  letter-spacing: -0.02em;
  line-height: 1;
  margin-bottom: 12px;
}
.stat-label {
  font-size: 16px;
  color: var(--tr-gray-60);
}
```

---

## 5. Service card (продуктовая карточка)

```html
<a class="service-card" href="#">
  <div class="service-illust"><img src="box.png" alt="" /></div>
  <span class="status status--active">Активно</span>
  <h3>Trely Shipping</h3>
  <p>Глобальная P2P доставка через сеть путешественников</p>
</a>
```
```css
.service-card {
  position: relative;
  display: block;
  background: var(--tr-white);
  border-radius: var(--r-xl);
  padding: 32px;
  box-shadow: var(--sh-soft);
  text-decoration: none;
  color: inherit;
  transition: box-shadow .2s, transform .2s;
}
.service-card:hover {
  box-shadow: var(--sh-medium);
  transform: translateY(-2px);
}
.service-illust { aspect-ratio: 1; margin-bottom: 24px; }
.service-illust img { width: 100%; height: 100%; object-fit: contain; }
.service-card h3 { font-size: 24px; font-weight: 600; margin: 0 0 8px; }
.service-card p { color: var(--tr-gray-60); font-size: 16px; margin: 0; }
```

### Status pill (в углу карточки)
```css
.status {
  position: absolute; top: 20px; right: 20px;
  font-size: 13px; font-weight: 500;
  padding: 6px 12px;
  border-radius: var(--r-pill);
}
.status--active { background: var(--tr-tag); color: var(--tr-green); }
.status--soon   { background: #F0EEEA; color: var(--tr-gray-60); }
.status--planned{ background: #F0EEEA; color: var(--tr-gray-40); }
```

---

## 6. Nav pills (top-bar активной навигации в pitch deck)

```html
<nav class="nav-pills">
  <a>О нас</a>
  <a class="active">Продукт</a>
  <a>Бизнес-модель</a>
  <a>Предложение</a>
</nav>
```
```css
.nav-pills { display: flex; gap: 8px; }
.nav-pills a {
  font-size: 15px;
  font-weight: 500;
  color: var(--tr-gray-60);
  padding: 8px 18px;
  border-radius: var(--r-pill);
  text-decoration: none;
}
.nav-pills a.active {
  background: var(--tr-tag);
  color: var(--tr-green);
}
```

---

## 7. Inline-tag в заголовке

```html
<h1>Сделать жизнь <span class="tag-inline">независимой</span> от места</h1>
```
```css
.tag-inline {
  background: var(--tr-tag);
  color: var(--tr-green);
  padding: 0 16px;
  border-radius: var(--r-pill);
  display: inline-block;
  /* совпадает по высоте со строкой */
}
```

---

## 8. Steps (шаги "Как это работает")

```html
<ol class="steps">
  <li><span>1</span><h4>Создать заявку</h4><p>Опишите маршрут и посылку</p></li>
  <li><span>2</span><h4>Найти попутчика</h4><p>Выберите по рейтингу</p></li>
  <li><span>3</span><h4>Передать</h4><p>Из рук в руки безопасно</p></li>
  <li><span>4</span><h4>Оплатить</h4><p>После доставки</p></li>
</ol>
```
```css
.steps { display: grid; grid-template-columns: repeat(4, 1fr); gap: 24px; list-style: none; padding: 0; }
.steps li { text-align: left; }
.steps span {
  display: inline-flex; align-items: center; justify-content: center;
  width: 48px; height: 48px;
  border-radius: 50%;
  background: var(--tr-gold);
  color: var(--tr-ink);
  font-weight: 700;
  font-size: 20px;
  margin-bottom: 16px;
}
.steps h4 { font-size: 18px; font-weight: 600; margin: 0 0 4px; }
.steps p { color: var(--tr-gray-60); font-size: 15px; margin: 0; }
```

---

## 9. QR-card (для slide-карточек продуктов)

```html
<div class="qr-card">
  <img src="qr.png" alt="QR" />
</div>
```
```css
.qr-card {
  background: var(--tr-white);
  padding: 20px;
  border-radius: var(--r-lg);
  display: inline-block;
  box-shadow: var(--sh-soft);
}
.qr-card img { width: 160px; height: 160px; display: block; }
```

---

## 10. Header сайта

```html
<header class="site-header">
  <a class="site-logo" href="/"><img src="logo-cube.svg" alt="" /><span>Trely</span></a>
  <nav class="site-nav">
    <a>Отправить / Доставить</a>
    <a>Объявления</a>
  </nav>
  <div class="site-actions">
    <span class="lang">RU</span>
    <button class="btn-primary">Войти</button>
  </div>
</header>
```
```css
.site-header {
  display: flex; align-items: center; justify-content: space-between;
  padding: 20px 64px;
  background: var(--tr-cream);
  position: sticky; top: 0; z-index: 10;
  backdrop-filter: blur(8px);
}
.site-logo { display: flex; align-items: center; gap: 10px; text-decoration: none; color: var(--tr-ink); font-weight: 700; font-size: 22px; }
.site-logo img { width: 32px; height: 32px; }
.site-nav { display: flex; gap: 32px; }
.site-nav a { color: var(--tr-ink); font-size: 15px; font-weight: 500; text-decoration: none; }
.site-actions { display: flex; align-items: center; gap: 16px; }
.lang { font-size: 14px; color: var(--tr-gray-60); }
```

---

## 11. Hero section (лендинг)

```html
<section class="hero">
  <div class="hero-text">
    <h1>Trely — твой мир путешествий <span class="gold">в одном месте</span></h1>
    <p>Мы создаём экосистему сервисов: от доставки посылок и поиска попутчиков до клубов, жилья и знакомств.</p>
    <div class="hero-cta">
      <button class="btn-primary">Отправить / Доставить</button>
      <button class="btn-secondary">Узнать больше</button>
    </div>
    <div class="brand-divider">Move <span>|</span> Live <span>|</span> Connect</div>
  </div>
  <div class="hero-illust">
    <div class="arc"></div>
    <img src="mascot.png" alt="" />
  </div>
</section>
```
```css
.hero { display: grid; grid-template-columns: 1fr 1fr; gap: 64px; padding: 80px 96px; align-items: center; }
.hero h1 { font-size: clamp(48px, 6vw, 80px); font-weight: 700; line-height: 1.05; letter-spacing: -0.02em; margin: 0 0 24px; }
.hero h1 .gold { color: var(--tr-gold); }
.hero p { font-size: 20px; line-height: 1.5; color: var(--tr-gray-60); margin: 0 0 40px; max-width: 540px; }
.hero-cta { display: flex; gap: 16px; margin-bottom: 32px; }
.brand-divider { font-size: 16px; color: var(--tr-gray-60); letter-spacing: 0.04em; }
.brand-divider span { color: var(--tr-gray-40); margin: 0 12px; }

.hero-illust { position: relative; aspect-ratio: 1; }
.hero-illust .arc {
  position: absolute; inset: 5%;
  border-radius: 50%;
  background: var(--tr-cream-sub);
  opacity: 0.5;
}
.hero-illust img { position: relative; width: 100%; height: 100%; object-fit: contain; }
```

---

## 12. Footer

```html
<footer class="site-footer">
  <div class="footer-left">
    <img src="logo-cube.svg" alt="" />
    <span>Trely, 2026 — Все права защищены</span>
  </div>
  <div class="footer-links">
    <a>Политика конфиденциальности</a>
    <a>Пользовательское соглашение</a>
    <a>Telegram</a>
    <a>WhatsApp</a>
  </div>
</footer>
```
```css
.site-footer { display: flex; justify-content: space-between; padding: 48px 64px; background: var(--tr-cream); }
.footer-left { display: flex; align-items: center; gap: 12px; color: var(--tr-gray-60); font-size: 14px; }
.footer-links { display: flex; gap: 24px; }
.footer-links a { color: var(--tr-gray-60); font-size: 14px; text-decoration: none; }
```

---

## 13. Loyalty/Subscription card (Базовый / Premier / Elite)

Используй для блока с тарифами — карточки в стиле "слиток золота".

```html
<div class="tier-card tier--elite">
  <div class="tier-cube">📦</div>
  <h4>Trely</h4>
  <small>Elite</small>
  <div class="tier-price">по приглашению</div>
  <ul>
    <li>Персональный менеджер</li>
    <li>Эксклюзивные офферы</li>
    <li>Повышенные лимиты</li>
  </ul>
</div>
```
```css
.tier-card {
  background: linear-gradient(180deg, #1A2F2F 0%, #0F1B1C 100%);
  border-radius: var(--r-xl);
  padding: 32px;
  color: var(--tr-white);
  position: relative;
  overflow: hidden;
}
.tier-card.tier--basic   { /* lighter gold accents */ }
.tier-card.tier--premier { border: 1px solid var(--tr-gold); }
.tier-card.tier--elite   { background: linear-gradient(180deg, #C6A064 0%, #8C6F3F 100%); color: var(--tr-ink); }
.tier-cube { font-size: 48px; margin-bottom: 16px; color: var(--tr-gold); }
.tier-price { font-size: 28px; font-weight: 700; margin: 16px 0; }
.tier-card ul { list-style: none; padding: 0; font-size: 15px; line-height: 1.6; opacity: 0.9; }
```

---

## 14. Gold-gradient Telegram button (header / footer CTA)

Заметный паттерн на trely.io — header и footer имеют gold-gradient pill вместо обычной dark кнопки.

```html
<a class="btn-gold-gradient" href="https://t.me/trely">Telegram</a>
```
```css
.btn-gold-gradient {
  display: inline-block;
  background: linear-gradient(90deg, #D4B57A 0%, #A8854F 100%);
  color: #FFFFFF;
  font-weight: 600;
  font-size: 15px;
  padding: 12px 28px;
  border-radius: var(--r-pill);
  text-decoration: none;
  box-shadow: 0 2px 12px rgba(168, 133, 79, .25);
  transition: transform .15s;
}
.btn-gold-gradient:hover { transform: translateY(-1px); }
/* Large variant — для footer */
.btn-gold-gradient--lg { padding: 16px 36px; font-size: 17px; }
```

---

## 15. Stat strip (4 метрики в hero)

Используется в продуктовых hero (Shipping route page).

```html
<div class="stat-strip">
  <div><span class="num">3-7 дней</span><span class="lbl">срок доставки</span></div>
  <div><span class="num">от $40</span><span class="lbl">тип. стоимость</span></div>
  <div><span class="num">7 500 км</span><span class="lbl">расстояние</span></div>
  <div><span class="num">Ежедневно</span><span class="lbl">рейсы</span></div>
</div>
```
```css
.stat-strip { display: grid; grid-template-columns: repeat(4, 1fr); gap: 0; margin: 32px 0; }
.stat-strip > div { padding: 16px 24px; border-right: 1px solid #E5E2DC; }
.stat-strip > div:last-child { border-right: none; }
.stat-strip .num { display: block; font-size: 24px; font-weight: 700; color: var(--tr-gold); letter-spacing: -0.01em; }
.stat-strip .lbl { display: block; font-size: 14px; color: var(--tr-gray-60); margin-top: 4px; }
```

---

## 16. Dark green route card (маршрут с метриками)

```html
<section class="route-card">
  <h2>Маршрут доставки из Москвы в Нью-Йорк</h2>
  <div class="route-line">
    <div class="route-end">
      <strong>Москва</strong>
      <small>SVO · DME · VKO</small>
    </div>
    <div class="route-mid">
      <span class="route-distance">7 500 км</span>
      <svg class="route-plane" viewBox="0 0 24 24" fill="#C6A064"><path d="M2 12l20-8-8 20-2-9-10-3z"/></svg>
    </div>
    <div class="route-end">
      <strong>Нью-Йорк</strong>
      <small>JFK · EWR · LGA</small>
    </div>
  </div>
  <div class="route-stats">
    <div><span>7 500 км</span><small>расстояние</small></div>
    <div><span>10-12 ч</span><small>в пути</small></div>
    <div><span>Ежедневно</span><small>отправления</small></div>
    <div><span>Стамбул, Дубай</span><small>пересадки</small></div>
  </div>
</section>
```
```css
.route-card { background: var(--tr-green); color: var(--tr-cream); border-radius: 32px; padding: 56px; margin: 48px 0; }
.route-card h2 { color: #fff; font-size: 36px; margin-bottom: 32px; }
.route-line { display: grid; grid-template-columns: 1fr auto 1fr; align-items: center; gap: 32px; padding: 24px 0; border-bottom: 1px solid rgba(255,255,255,.1); }
.route-end strong { display: block; font-size: 28px; color: #fff; }
.route-end small { color: var(--tr-gray-60); font-size: 14px; }
.route-mid { text-align: center; }
.route-distance { color: var(--tr-gold); font-size: 32px; font-weight: 700; display: block; }
.route-plane { width: 32px; height: 32px; margin-top: 8px; }
.route-stats { display: grid; grid-template-columns: repeat(4, 1fr); gap: 24px; padding-top: 24px; }
.route-stats span { display: block; color: var(--tr-gold); font-size: 22px; font-weight: 700; }
.route-stats small { color: var(--tr-gray-60); font-size: 14px; }
```

---

## 17. Featured service pair (Shipping + Car style на главной)

2 крупных карточки в ряд — одна тёмная, одна светлая.

```html
<div class="feature-pair">
  <a class="featured featured--dark">
    <div>
      <h3>Trely Shipping</h3>
      <p>Передавайте посылки так, будто везёте их лично. С Trely доставка становится быстрее, надёжнее и выгоднее.</p>
      <button class="btn-primary">Отправить/Доставить</button>
    </div>
    <img src="/illustrations/char-shipping.png" alt="" />
  </a>
  <a class="featured featured--light">
    <div>
      <h3>Trely Car</h3>
      <p>Ваши путешествия — с комфортом и надёжными попутчиками. Trely соединяет людей, которые по пути.</p>
      <button class="btn-primary">Поехать</button>
    </div>
    <img src="/illustrations/char-car.png" alt="" />
  </a>
</div>
```
```css
.feature-pair { display: grid; grid-template-columns: 1fr 1fr; gap: 24px; }
.featured { display: grid; grid-template-columns: 1.2fr 1fr; gap: 24px; align-items: center; padding: 40px; border-radius: 28px; text-decoration: none; min-height: 280px; }
.featured--dark { background: var(--tr-green); color: var(--tr-cream); }
.featured--dark h3 { color: #fff; font-size: 28px; }
.featured--dark p { color: rgba(255,255,255,.75); margin: 12px 0 24px; }
.featured--light { background: var(--tr-white); color: var(--tr-ink); box-shadow: var(--sh-soft); }
.featured--light h3 { font-size: 28px; }
.featured--light p { color: var(--tr-gray-60); margin: 12px 0 24px; }
.featured img { width: 100%; height: auto; object-fit: contain; }
```

---

## 18. Two-col trust table (с золотыми чек-марками)

```html
<div class="trust-table">
  <div>
    <span class="cat-pill">🇺🇸 Таможня США</span>
    <ul>
      <li>Стоимость до $800 — без декларации</li>
      <li>Свыше $800 — требуется заполнение декларации</li>
      <li>Личные вещи проходят без обложения пошлиной</li>
    </ul>
  </div>
  <div>
    <span class="cat-pill gold">📦 Требования к упаковке</span>
    <ul>
      <li>Надёжная упаковка от ударов</li>
      <li>Хрупкие предметы — в коробку с амортизатором</li>
      <li>Электроника — заряд не более 30%</li>
    </ul>
  </div>
</div>
```
```css
.trust-table { display: grid; grid-template-columns: 1fr 1fr; gap: 48px; padding: 48px 0; }
.cat-pill { display: inline-block; background: var(--tr-tag); color: var(--tr-green); font-weight: 600; padding: 6px 16px; border-radius: var(--r-pill); font-size: 14px; margin-bottom: 16px; }
.cat-pill.gold { background: rgba(198,160,100,.2); color: #8C6F3F; }
.trust-table ul { list-style: none; padding: 0; }
.trust-table li { padding: 10px 0 10px 32px; position: relative; color: var(--tr-ink); font-size: 16px; }
.trust-table li::before { content: '✓'; position: absolute; left: 0; top: 10px; color: var(--tr-gold); font-weight: 700; font-size: 18px; }
```

---

## 19. Category card (6-up с иллюстрацией)

```html
<div class="cat-grid">
  <a class="cat-card">
    <img src="/obj/documents.png" alt="" />
    <h4>Документы</h4>
    <span class="link-gold">Смотреть →</span>
  </a>
  <!-- ×6 -->
</div>
```
```css
.cat-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; }
.cat-card { display: block; background: #F4F1EA; border-radius: 20px; padding: 24px; text-decoration: none; color: inherit; aspect-ratio: 3/2; position: relative; transition: transform .15s; }
.cat-card:hover { transform: translateY(-2px); }
.cat-card img { width: 60%; height: 60%; object-fit: contain; position: absolute; right: 16px; bottom: 16px; }
.cat-card h4 { font-size: 20px; font-weight: 600; }
.link-gold { color: var(--tr-gold); font-size: 14px; font-weight: 500; }
@media (max-width: 768px) { .cat-grid { grid-template-columns: 1fr 1fr; } }
```

---

## 20. FAQ accordion

```html
<details class="faq-item">
  <summary>Как работает доставка?</summary>
  <p>Вы создаёте заявку, выбираете попутчика по маршруту и рейтингу, договариваетесь о деталях в чате…</p>
</details>
```
```css
.faq-item {
  border-bottom: 1px solid #E5E2DC;
  padding: 24px 0;
}
.faq-item summary {
  font-size: 18px;
  font-weight: 600;
  cursor: pointer;
  list-style: none;
  display: flex; justify-content: space-between;
}
.faq-item summary::after { content: '+'; color: var(--tr-gold); font-size: 24px; }
.faq-item[open] summary::after { content: '−'; }
.faq-item p { color: var(--tr-gray-60); margin: 16px 0 0; line-height: 1.6; }
```
