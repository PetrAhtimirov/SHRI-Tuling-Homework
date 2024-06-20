# SHRI-Tuling-Homework

## Network анализ

### Запись network - `./rigla-network.har`

### Дублирующиеся запросы

Запрос к graphql повторяется 9 раз.

*Но это пост запрос, в котором мы отсылаем разные body, так что есть смысл дублировать его.

<img src="./img/network-duplicates.png" style="max-width: 850px" alt="">

### Лишний размер ресурса

JS скрипты имеют большой размер, т.к. плохо разбиты на chunks.
Стоит отметить, что в топе больших скриптов всего 2 написанных на сайте: `my-repices.js_t=2511940e` и
`chunk-07046ba1.js?_t=45c65d99`.
Наиболее большие скрипты приведены ниже.

<img src="./img/network-oversize-js.png" style="max-width: 850px" alt="">

Изображения имеют большой размер, т.к. используются неоптимизированный формат (как .png или .jpg).
Наиболее большие изображения представлены ниже.

<img src="./img/network-oversize-img.png" style="max-width: 850px" alt="">

### Ресурсы блокирующие отображение

Ресурсы блокирующие отображение - `app.js?_t=01971f7a` и `chunk-vendors.js?_t=9f02fabd`

<img src="./img/network-blocking.png" style="max-width: 850px" alt="">

### Еще неоптимальные места

Ошибка - 
запрос, заблокированный CORS политикой

<img src="./img/more-errors.png" style="max-width: 840px" alt="">

## Performance анализ

### Запись Performance - `./rigla-performance.json`

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

### Скриншот вкладки после открытия страницы
<img src="./img/coverage-screenshot.png" style="max-width: 900px" alt="">

### Объем неиспользованного CSS
45.9 kB не использовано

<img src="./img/css-coverage.png" style="max-width: 900px" alt="">

### Объем неиспользованного JS
3.5 mB - 3584 kB не использовано

<img src="./img/js-coverage.png" style="max-width: 900px" alt="">

# Дополнительное задание

## Network анализ

### Запись network - `./rigla-second-network.har`

Результаты network анализа принципиально ничем не отличаются от основного задания,
кроме времени выполнения запросов.

## Performance анализ

### Запись Performance - `./rigla-second-performance.json`

### Измерение времени от начала навигации до событий
- DOM Content Loaded (DCL) - 3430.5 ms
- First Paint (FP) - 17192.2 ms
- First Contentful Paint (FCP) - 17192.2 ms
- Load (L) - 71466.4 ms
- Largest Contentful Paint (LCP) - 66938.9 ms

<img src="./img/second-events-timing.png" style="max-width: 900px" alt="">

### LCP
Largest Contentful Paint (LCP) происходит на изображении:

`<img src="https://cdn.rigla.ru/media/tj_banner/images/66421b88d42317.83283372.jpg" alt="image" class="js-image">`

<img src="./img/second-LCP-element.png" style="max-width: 320px" alt="">
<img src="./img/LCP-DOM.png" style="max-width: 530px" alt="">

### Этапы обработки документа
- Loading - 33 ms
- Scripting - 3199 ms
- Rendering - 652 ms
- Painting - 390 ms

<img src="./img/second-perfomance-summary.png" style="max-width: 400px" alt="">

## Coverage анализ

Результаты coverage анализа принципиально ничем не отличаются от основного задания,
кроме времени подгрузки файлов.