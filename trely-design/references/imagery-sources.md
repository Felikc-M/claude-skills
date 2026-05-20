# TRELY — Фотографии направлений и реальные изображения

Когда на странице нужно **реальное фото места** (Бали, Париж, Нью-Йорк, Кейптаун) — например, секция «Популярные направления» на shipping.trely.io.

## 🚨 Главное правило

**НЕ оставляй placeholder'ы вроде `<img src="bali.jpg" />` без реального источника.** Это убивает доверие к макету. Всегда:
1. Бери прямую ссылку из Unsplash (CDN-урл, см. ниже)
2. Или через Unsplash Source API (динамическая ссылка)
3. Или генерируй промт для Nano Banana Pro в фирменной стилизации

---

## Источник №1 — Unsplash Source (динамические ссылки)

Самый быстрый способ — Unsplash Source API. Просто URL с ключевыми словами:

```html
<!-- Конкретный город -->
<img src="https://source.unsplash.com/800x600/?bali,beach" alt="Бали" />

<!-- Несколько ключей -->
<img src="https://source.unsplash.com/1200x800/?paris,eiffel,sunset" alt="Париж" />
```

**Преимущества:** работает сразу, разные изображения каждую загрузку, легально бесплатно.
**Минус:** не контролируешь точное фото — может выпасть случайное по тегу.

### Готовые URL для популярных направлений TRELY

```
Бали:           https://source.unsplash.com/1200x800/?bali,temple,rice-terrace
Таиланд:        https://source.unsplash.com/1200x800/?thailand,phi-phi,beach
Стамбул:        https://source.unsplash.com/1200x800/?istanbul,bosphorus,mosque
Дубай:          https://source.unsplash.com/1200x800/?dubai,skyline,burj-khalifa
Нью-Йорк:       https://source.unsplash.com/1200x800/?new-york,manhattan,brooklyn-bridge
Париж:          https://source.unsplash.com/1200x800/?paris,eiffel,seine
Лондон:         https://source.unsplash.com/1200x800/?london,big-ben,tower-bridge
Москва:         https://source.unsplash.com/1200x800/?moscow,red-square,kremlin
Кейптаун:       https://source.unsplash.com/1200x800/?cape-town,table-mountain
Тбилиси:        https://source.unsplash.com/1200x800/?tbilisi,georgia
Ереван:         https://source.unsplash.com/1200x800/?yerevan,armenia
Алматы:         https://source.unsplash.com/1200x800/?almaty,kazakhstan,mountains
Ташкент:        https://source.unsplash.com/1200x800/?tashkent,uzbekistan
Барселона:      https://source.unsplash.com/1200x800/?barcelona,sagrada-familia
Лиссабон:       https://source.unsplash.com/1200x800/?lisbon,portugal
Берлин:         https://source.unsplash.com/1200x800/?berlin,brandenburg-gate
```

---

## Источник №2 — Pexels (альтернатива)

Когда Unsplash отдаёт неподходящее:

```
https://www.pexels.com/search/[query]/
```

Найти, скопировать прямой URL изображения, использовать. Также бесплатно.

---

## Источник №3 — Pixabay (free for commercial)

```
https://pixabay.com/photos/search/[query]/
```

---

## Готовые HTML-блоки для секции «Популярные направления»

```html
<section class="destinations">
  <h2>Популярные направления</h2>
  <div class="dest-grid">
    <a class="dest-card">
      <img src="https://source.unsplash.com/600x400/?bali,temple" alt="Бали" />
      <span class="dest-pill">Бали</span>
    </a>
    <a class="dest-card">
      <img src="https://source.unsplash.com/600x400/?thailand,beach" alt="Таиланд" />
      <span class="dest-pill">Таиланд</span>
    </a>
    <a class="dest-card">
      <img src="https://source.unsplash.com/600x400/?paris,eiffel" alt="Париж" />
      <span class="dest-pill">Париж</span>
    </a>
    <a class="dest-card">
      <img src="https://source.unsplash.com/600x400/?cape-town,table-mountain" alt="Кейптаун" />
      <span class="dest-pill">Кейптаун</span>
    </a>
  </div>
</section>
```
```css
.dest-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 16px; }
.dest-card {
  position: relative;
  display: block;
  aspect-ratio: 3/4;
  border-radius: 24px;
  overflow: hidden;
  text-decoration: none;
}
.dest-card img {
  width: 100%; height: 100%;
  object-fit: cover;
  transition: transform .4s;
}
.dest-card:hover img { transform: scale(1.05); }
.dest-pill {
  position: absolute;
  left: 16px; bottom: 16px;
  background: rgba(247,246,244,.95);
  color: var(--tr-green);
  padding: 8px 20px;
  border-radius: 999px;
  font-weight: 600;
  font-size: 16px;
}
```

---

## Источник №4 — AI-генерация в стиле Trely

Когда нужен **фирменно-стилизованный** вид места (не сток, а часть бренда):

### Промт-шаблон для Nano Banana Pro / Midjourney

```
Painterly digital illustration of [LOCATION] iconic landscape, watercolor and
gouache texture, warm natural lighting, brand palette deep forest green
#273C3F, warm gold #C6A064, soft cream #F7F6F4 with allowed denim blue and
tan accents. Cozy traveler aesthetic, semi-realistic, no harsh outlines,
no flat vector, no 3D render, no photoreal. --ar 3:4 --style raw
```

Подстановки для популярных направлений:
- **Bali:** *rice terraces with traditional Balinese temple, palm trees, golden hour*
- **Paris:** *Eiffel Tower silhouette from Seine river, summer evening*
- **Istanbul:** *Bosphorus view with Hagia Sophia minarets at dusk*
- **Dubai:** *desert dunes with Burj Khalifa silhouette, sunset*
- **New York:** *Brooklyn Bridge with Manhattan skyline, autumn morning*
- **Cape Town:** *Table Mountain view from Camps Bay beach*
- **Tbilisi:** *Old town narrow streets with sulfur baths domes, autumn*

Этот вариант **лучше для главной обложки** или ad-креативов — выглядит как часть Trely, а не sticker. Сток-фото — для длинных списков направлений.

---

## Решение «Когда что»

| Контекст | Что использовать |
|---|---|
| Карусель «Популярные направления» (4-8 карточек) | Unsplash Source URLs |
| Hero обложка про конкретное место | AI-стилизация (Nano Banana) |
| OG-картинка маршрутной страницы | AI-стилизация |
| Список из 20+ направлений | Unsplash Source (динамически) |
| Reels-обложка | AI-стилизация + персонаж TRELY |
| Карта мира с пинами | Минималистичная стилизация (deep green + gold pins) |
| Документы / Электроника / Одежда (категории посылок) | Painterly иллюстрация в стиле Trely (см. `prompts/illustrations.md` — категории Trely Shop) |

---

## ❌ Не используй

- Дешёвые stock-photos с водяными знаками
- Чужие тревел-блогерские фото без лицензии
- Фото с людьми (privacy, лицензии)
- HDR / overedited / Instagram-стилизованные фото с «эффектами»
- 3D-рендеры или CGI городов

---

## Кеширование (для prod)

Когда лендинг идёт в продакшен — **скачай Unsplash изображения локально** в `public/photos/destinations/` и используй их. Динамическая ссылка не выдержит нагрузки и Unsplash не гарантирует тот же кадр.

Скрипт-набросок:
```bash
mkdir -p public/photos/destinations
for city in bali paris istanbul dubai new-york; do
  curl -L "https://source.unsplash.com/1600x1200/?$city" -o "public/photos/destinations/$city.jpg"
done
```
