# TRELY — Логотип (официальные ассеты)

Все SVG/PNG взяты из официального брендбука Trely (источник: iCloud / Trely лого/).

## Файлы

| Файл | Что | Когда использовать |
|---|---|---|
| `trely-black.svg` / `Trely black.png` | Wordmark "Trely" чёрный | На светлом фоне (cream/white). Основной вариант. |
| `trely-white.svg` / `Trely white.png` | Wordmark "Trely" белый | На тёмно-зелёном или чёрном фоне. |
| `trely-gold-gradient.svg` / `Дополнительный Trely gold gradient.png` | Wordmark с золотым градиентом (от тёмного к gold слева→направо, "y" — самая светлая) | Парадные обложки, hero-секции, premium-контекст. Не для UI-чипов. |
| `trely-full-illustration.svg` / `Лого с картинкой.png` (см. Desktop/Trely) | Полный знак: куб-иллюстрация + wordmark снизу | Обложка презентации, OG-картинка, splash screen |
| `trely-letter-variants.svg` / `Разные буквы.png` | Альтернативные начертания букв | Только как референс. Для production использовать основной. |

## Wordmark — анатомия

- Шрифт: **Inter Tight Medium/Regular** (открытая буква "y", без хвоста-завитка)
- Базовая высота строчной = высоте знака-куба
- Расстояние между знаком и wordmark в комбо ≈ половина высоты "T"

## Цветовые правила

| Фон | Логотип |
|---|---|
| `#F7F6F4` cream | `trely-black.svg` или `trely-gold-gradient.svg` |
| `#FFFFFF` white | `trely-black.svg` |
| `#273C3F` deep green | `trely-white.svg` или золотая версия |
| `#0F1014` near-black | `trely-white.svg` или золотая версия |
| Золотой `#C6A064` фон | `trely-black.svg` |

## ❌ Запрещено (из брендбука)

- Не менять типографику (✗ другой шрифт)
- Не менять пропорции между знаком и wordmark
- Не использовать неутверждённые цвета (✗ оранжевый — пример в брендбуке)
- Не сжимать и не искажать
- Не добавлять обводки / тени / эффекты

## Использование в HTML

```html
<!-- Inline SVG чёрный (вставь содержимое trely-black.svg) -->
<img src="/assets/logo/trely-black.svg" alt="Trely" height="32" />

<!-- Полный логотип для hero/обложки -->
<img src="/assets/logo/trely-full-illustration.svg" alt="Trely" />
```

## Минимальные размеры

- Wordmark: высота не меньше 20px (digital), 8mm (print)
- Полный логотип с кубом: высота не меньше 60px (digital), 20mm (print)

## Свободная зона (safe area)

Вокруг логотипа резервируй пустое пространство, равное **высоте буквы "T"** в wordmark. Никаких других элементов в этой зоне.
