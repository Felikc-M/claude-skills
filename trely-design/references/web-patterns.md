# TRELY — Веб-паттерны для лендингов и продуктовых сайтов

Основано на анализе trely.io (главный) и shipping.trely.io (продуктовый).

---

## Стандартная структура страницы

| Порядок | Секция | Обязательность |
|---|---|---|
| 1 | **Sticky header** | всегда |
| 2 | **Hero** с H1 + sub + 2 CTA + иллюстрацией маскота | всегда |
| 3 | **Сервисы / Продукт** (для главной) или **Подзадачи** (для продуктовой) | для главной |
| 4 | **Как это работает** (4 шага) | для продуктовых |
| 5 | **Популярные направления / Use cases** | опционально |
| 6 | **Почему нас выбирают** (3-4 фичи с gold иконками) | всегда |
| 7 | **Trust & безопасность** (Trust Core Trely) | для продуктовых |
| 8 | **Социальное доказательство** (отзывы / NPS / цифры) | опционально |
| 9 | **FAQ** (accordion) | всегда |
| 10 | **Final CTA-блок** | желательно |
| 11 | **Footer** | всегда |

---

## Header

### Поведение
- **Sticky** — приклеен к верху при скролле
- **Backdrop blur** на cream background при появлении скролла
- Border-bottom 1px очень светлый при scroll>10px

### Состав (слева → центр → справа)
1. Логотип-куб + слово "Trely" (clickable home)
2. Nav: 2-3 ключевых пункта + ссылки на основные продукты
3. Language switcher (RU/EN) + CTA "Войти" / "Регистрация"

### Mobile
Гамбургер слева, логотип по центру, CTA справа.

---

## Hero

### Layout
50/55 — текст слева, иллюстрация справа (на mobile — стек).

### Anatomy
1. **H1** (60-80px, Bold) — название продукта или value statement
   - С одним золотым акцентом или inline-пилюлей
2. **Sub** (20-22px, Regular gray) — 1-2 предложения
3. **Primary CTA** (dark BG) + **Secondary CTA** (outline)
4. **Brand divider** "Move | Live | Connect" под кнопками
5. **Illustration column** — маскот в круглой arc-композиции

### Trely.io hero пример
```
H1: «Trely — твой мир путешествий в одном месте»
Sub: «Мы создаём экосистему сервисов для путешественников: от доставки посылок и поиска попутчиков до клубов, жилья и знакомств.»
CTA1: Отправить / Доставить (dark)
CTA2: Узнать больше (outline)
```

### Shipping.trely.io hero пример
```
H1: «Надёжная доставка руками реальных людей»
Sub: «Зачем ждать и переплачивать? Найдите человека, который уже летит в нужный город — и доверьте ему доставку.»
CTA1: Отправить посылку (dark)
CTA2: Стать доставщиком (outline)
```

---

## Service grid (главная страница)

3 колонки × 2 ряда = до 6 карточек. Активные сервисы вначале, потом "Скоро".

### Карточка сервиса
- Status pill в правом-верхнем углу (Активно / Скоро)
- Quadrate illustration сверху (объект-иконка в стиле бренда)
- H3 название (Trely Shipping)
- Описание одной строкой

### Сервисы Trely (порядок)
1. Trely Shipping (Активно)
2. Trely Travel Club (Активно)
3. Trely Car (Скоро)
4. Trely Stay (Скоро)
5. Trely Shop (Скоро)
6. Trely Love (Скоро)

---

## "Как это работает" — 4 шага

Используй для всех продуктовых страниц. **Всегда 4 шага** для симметрии.

```
1 → 2 → 3 → 4
Создать → Найти → Передать → Оплатить
```

Каждый шаг: gold-круг с номером, заголовок Bold, описание Regular.

---

## "Почему нас выбирают"

3-4 преимущества в горизонтальном grid. Каждое:
- Gold иконка (опционально круглая)
- Bold заголовок
- 1-2 строки объяснения

Триггерные темы:
- **Безопасность сделок** — Escrow, Trust Core, KYC
- **Реальные люди** — verified, rating, photos
- **Глобально** — поддержка в 50+ странах
- **Поддержка 24/7** — chat, email, telegram

---

## Trust block (для продуктовых)

Особый блок "Trust Core Trely" — выделяется gold-обводкой или gold-фоном. Перечисляет:
- ✓ KYC проверка личности
- ✓ Escrow удержание денег
- ✓ Рейтинг и репутация
- ✓ Страхование операций

---

## FAQ

- Accordion (`<details>`)
- 5-8 вопросов
- Knapp summary | Полный ответ
- + / − индикатор золотым
- Лёгкие разделительные линии

---

## Final CTA

Перед футером — крупный блок:
```
[Heading]: "Готовы попробовать?"
[Sub]:     "Создайте заявку за 1 минуту"
[CTA]:     Primary большая кнопка
```
Можно с иллюстрацией маскота сбоку.

---

## Footer

- Cream фон, очень светлая border-top
- Слева: маленький cube + копирайт "Trely, 2026"
- Справа: 4-5 ссылок (Privacy, Terms, Telegram, WhatsApp, контакт)

---

## Mobile поведение

- Padding 24px по бокам
- Hero — стек (текст → иллюстрация)
- Service grid — 1 колонка (или 2 на tablet)
- Steps — 2×2 grid вместо 4×1
- FAQ — на всю ширину
- Header — hamburger menu, минимальный CTA

---

## Эффекты и анимации

- **Hover на карточке:** translateY(-2px) + shadow medium
- **Sticky header:** opacity + blur при scroll
- **FAQ:** smooth open/close
- **Buttons:** translateY(-1px) на hover
- Никаких parallax, никаких сложных WebGL — Trely-стиль медитативный и спокойный

---

## SEO meta (для каждой страницы)

```html
<title>Trely — твой мир путешествий в одном месте</title>
<meta name="description" content="Экосистема сервисов: P2P доставка, попутчики, клубы, жильё. Move. Live. Connect." />
<meta property="og:image" content="/og/main-mascot-cream.jpg" />
```

OG-картинки — главный маскот на cream с заголовком в Inter Tight.

---

## Файловая структура (рекомендация)

```
/public
  /logo
    cube-dark.svg
    cube-gold.svg
    wordmark.svg
  /illustrations
    mascot-main.png        # глав. маскот
    char-shipping.png      # бегущая женщина с коробкой
    char-car.png           # две девушки
    char-club.png          # мальчик в шляпе
    obj-box.png
    obj-plane.png
    obj-car.png
    obj-palm.png

/styles
  tokens.css               # из references/components.md
  global.css

/components
  Header.tsx
  Hero.tsx
  ServiceGrid.tsx
  Steps.tsx
  FAQ.tsx
  Footer.tsx
```
