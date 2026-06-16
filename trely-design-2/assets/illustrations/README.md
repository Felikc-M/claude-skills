# TRELY — Иллюстрации (готовые PNG)

Все файлы — извлечены напрямую из официального Trely Brandbook 2026, **с прозрачным фоном** (PNG with alpha). Готовы к использованию в макетах поверх любого фона.

## 🚨 ОБЯЗАТЕЛЬНОЕ ПРАВИЛО

**Не генерируй иллюстрации заново. Не используй stock-картинки. Не используй эмодзи вместо иллюстраций.** В любом макете TRELY (слайд, лендинг, ад-креатив, обложка) — **всегда** вставляй PNG из этой папки. Это часть бренда.

Промты в `prompts/illustrations.md` — только для случаев, когда нужен **новый** персонаж/сцена которой нет в этой папке. Для существующих — бери готовые.

---

## Характеры / Персонажи (`characters/`)

| Файл | Кто | Когда использовать | Пример |
|---|---|---|---|
| `01-mascot-main-blue.png` | Главный маскот TRELY — парень со смартфоном, тёмный синий свитер с золотыми пятнами | Hero обложки, splash, любая страница где нужен «лицо бренда». Версия для светлого фона | Pitch deck cover, главная trely.io |
| `02-mascot-main-green.png` | Тот же маскот в зелёном свитере | Альтернатива для cream фона с тёплым акцентом | Кадры рилс, OG-картинки |
| `03-shipping-boy-luggage.png` | Парень в синей футболке с чемоданом + 2 коробками | **Trely Shipping** — любая страница про доставку | shipping.trely.io hero, маршрутные страницы |
| `04-car-duo-girls.png` | Две девушки в синей машинке (рыжая водитель + темноволосая пассажир) | **Trely Car** — главный визуал | trely.io card "Trely Car", carpooling страницы |
| `05-car-driver-boy.png` | Парень-водитель в синей машинке вид сбоку | Trely Car — альтернативный визуал, B2B-водители | Лендинг "Стать водителем" |
| `06-travelclub-boy-bali.png` | Мальчик в шляпе и тропической рубашке с табличкой "Bali" | **Trely Travel Club / Services / Guides** — туристическая ниша | trely.io hero (главная), Travel Club лендинг |

## Объекты (`objects/`)

| Файл | Что | Когда использовать |
|---|---|---|
| `01-box-green-stars.png` | Картонная коробка зелёная со звёздочками и стикерами | Иконка Shipping в карточках сервисов, ад-креативы |
| `02-plane-green-gold.png` | Самолёт зелёно-золотой в облаках | Иконка авиа / маршрутов / Trely Avia |
| `03-car-green-mini.png` | Зелёная мини-машинка с золотыми колёсами | Иконка Trely Car в карточках |
| `04-palm-tropical.png` | Пальма с песком, кремовая палитра | Иконка Travel/Stay/Guides, тропические направления |

---

## Как использовать

### В HTML
```html
<!-- Hero -->
<img src="/assets/illustrations/characters/03-shipping-boy-luggage.png" alt="" />

<!-- Service card icon -->
<img src="/assets/illustrations/objects/01-box-green-stars.png" alt="" />
```

### В превью / Figma
Перетащи нужный файл из `~/.claude/skills/trely-design/assets/illustrations/`. Все 2048×2048 (характеры) или 1024×1024 (объекты) — масштабируй вниз.

### В композициях
- На cream/white фоне — вставляй напрямую, прозрачность работает
- На тёмно-зелёном фоне — те же файлы, прозрачность позволяет
- За иллюстрацией хорошо добавить полупрозрачную золотую/cream арку (см. компонент `.arc` в `references/components.md`)

---

## Мэппинг "Сервис → Какая иллюстрация"

| Сервис | Главный персонаж | Объект-иконка |
|---|---|---|
| Trely (общий / главная) | `02-mascot-main-green.png` или `06-travelclub-boy-bali.png` | — |
| Trely Shipping | `03-shipping-boy-luggage.png` | `01-box-green-stars.png` |
| Trely Car | `04-car-duo-girls.png` | `03-car-green-mini.png` |
| Trely Travel Club | `06-travelclub-boy-bali.png` | `04-palm-tropical.png` |
| Trely Services / Guides | `06-travelclub-boy-bali.png` | `04-palm-tropical.png` |
| Trely Stay | `06-travelclub-boy-bali.png` | — (или дом, новая нужна) |
| Trely Avia (план) | `01-mascot-main-blue.png` | `02-plane-green-gold.png` |
| Trely Shop (план) | `02-mascot-main-green.png` | `01-box-green-stars.png` |
| Trely Love (план) | `02-mascot-main-green.png` | — (новая нужна) |

---

## Чего НЕТ — куда смотреть

Если нужен персонаж/объект, которого нет в папке — открой `prompts/illustrations.md` и сгенерь через Nano Banana Pro / Midjourney со встроенным suffix-стилем. Сохрани результат в эту папку, чтобы скилл рос.

Что вероятно потребуется добавить:
- Stay-маскот (девушка с чемоданом перед домом)
- Love-сцена (двое в кафе)
- Shop-маскот (с пакетами)
- Чемодан (отдельный объект)
- Здание/отель (объект для Stay)
- Глобус (для экосистемы)
- Деньги/обмен валют (для Services)
