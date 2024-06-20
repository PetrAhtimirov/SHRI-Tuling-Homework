# SHRI-Tuling-Homework

## Network анализ

### Дублирующиеся запросы

Запрос к graphql повторяется 9 раз

<img src="./img/network-duplicates.png" style="max-width: 900px" alt="">

### Лишний размер ресурса

Можно отметить ресурс `my-recipes.js?_t=2511940e`, который имеет большой размер и блокирует рендеринг.

Изображения имеют большой размер, т.к. используются неоптимизированный формат (как .png или .jpg).
Наиболее большие изображения также представлены ниже.

<img src="./img/network-oversize.png" style="max-width: 900px" alt="">

### Ресурсы блокирующие отображение

Ресурсы блокирующие отображение - `/js/app.js?_t=01971f7a` и `/js/chunk-vendors.js?_t=9f02fabd`

<img src="./img/network-blocking.png" style="max-width: 900px" alt="">

## Perfomance анализ

### Запись Perfomance - `./rigla-perfomance.json`

### Измерение времени от начала навигации до событий
 - DOM Content Loaded (DCL) - 456.2 ms
 - First Paint (FP) - 918.12 ms
 - First Contentful Paint (FCP) - 918.12 ms
 - Load (L) - 1178.8 ms
 - Largest Contentful Paint (LCP) - 1823.9 ms

<img src="./img/events-timing.png" style="max-width: 900px" alt="">

### LCP
Largest Contentful Paint (LCP) происходит на изображении:

`<img src="https://cdn.rigla.ru/media/tj_banner/images/66421b88d42317.83283372.jpg" alt="image" class="js-image">`

<img src="./img/LCP-element.png" style="max-width: 320px" alt="">
<img src="./img/LCP-DOM.png" style="max-width: 530px" alt="">

### Этапы обработки документа
 - Loading - 3 ms
 - Scripting - 408 ms
 - Rendering - 17 ms
 - Painting - 1 ms

<img src="./img/perfomance-summary.png" style="max-width: 400px" alt="">

## Coverage анализ

### Запись Coverage - `./rigla-coverage.json`

### Скриншот вкладки после открытия страницы
<img src="./img/coverage-screenshot.png" style="max-width: 900px" alt="">

### Объем неиспользованного CSS
45.9 kB не использовано

<img src="./img/css-coverage.png" style="max-width: 900px" alt="">

### Объем неиспользованного JS
3.5 mB - 3584 kB не использовано

<img src="./img/js-coverage.png" style="max-width: 900px" alt="">
