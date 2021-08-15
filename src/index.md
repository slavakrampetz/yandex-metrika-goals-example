---
title: Как использовать цели Яндекс.Метрики для получения статистика по разделам сайта
layout: page
---
# Как использовать цели Яндекс.Метрики для получения статистика по разделам сайта

Используем существующий счётчик Яндекс.Метрики или заводим новый.
Все примеры - на базе сайта https://ltr.online-media.ru/.

### Шаг 1. Подготовка

1. Завёл новый счётчик для сайта, код:

```
<!-- Yandex.Metrika counter -->
<script type="text/javascript" >
   (function(m,e,t,r,i,k,a){m[i]=m[i]||function(){(m[i].a=m[i].a||[]).push(arguments)};
   m[i].l=1*new Date();k=e.createElement(t),a=e.getElementsByTagName(t)[0],k.async=1,k.src=r,a.parentNode.insertBefore(k,a)})
   (window, document, "script", "https://mc.yandex.ru/metrika/tag.js", "ym");

   ym(84013735, "init", {
        clickmap:true,
        trackLinks:true,
        accurateTrackBounce:true
   });
</script>
<noscript><div><img src="https://mc.yandex.ru/watch/84013735" style="position:absolute; left:-9999px;" alt="" /></div></noscript>
<!-- /Yandex.Metrika counter -->
```

2. Исправляем код, если требуется.

3. Выделяем ID счётчика. ID счётчика: 84013735

4. Вставляем счётчик в админку
   [01.counter-in-settings.png]


### Шаг 2. 
