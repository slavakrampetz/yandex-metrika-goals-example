---
title: Как использовать цели Яндекс.Метрики для получения статистика по разделам сайта
layout: page
---
# Как использовать цели Яндекс.Метрики для получения статистика по разделам сайта

Используем существующий счётчик Яндекс.Метрики или заводим новый.
Все примеры - на базе сайта https://ltr.online-media.ru/.

### Шаг 1. Подготовка

Завести новый счётчик для сайта, https://metrika.yandex.ru/dashboard?id=84013735
Код:
```html
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
- Исправить код, если требуется.
- Выделить ID счётчика. ID счётчика: `84013735`. 
- [Вставить счётчик](img/01.counter-in-settings.png) в админку, https://ltr.online-media.ru/cms/
- Проверить, что код выводится: `Ctrl+U` в браузере, ищем код счётчика.

### Шаг 2. Создание целей

Создать цели на каждую группу, https://metrika.yandex.ru/goals?id=84013735

Пример, [скриншот](img/02.goal-create-ym.png):

- Название: Из фонда Музей Томского приборного завода
- Тип: JavaScript-событие
- Идентификатор цели: `elib-tomsk-instruments-2021`
  <br>**важно**: суффикс идентификатора цели формировать из `год-месяц`, пригодится позже
- Скопировать код 
- Добавить цель, сохранить счётчик

Результат: [список целей](img/03.goals.png)

Скопированный код:
```javascript
ym(84013735,'reachGoal','elib-tomsk-instruments-2021')
```

### Шаг 3. Использование целей

На нужной странице (документе) надо разместить скопированный код.

Сформировать код для вставки в HTML:
```html
<script defer>
  document.addEventListener("DOMContentLoaded", function () {
    ym(84013735,'reachGoal','elib-tomsk-instruments-2021')
  });
</script>
```
Вставить в страницу.

Проверить результат:

1. Выводится ли код на нужной странице? 
  <br>`Ctrl + U`: [скриншот](img/10.goal-in-source.png)
2. Нет ли ошибок в консоли инструментов разработчика?<br>`F12` -> Console: [скриншот](img/11.page-dev-console.png)


### Шаг 4. Аналитика

Открыть Яндекс.Метрика, счётчик.
https://metrika.yandex.ru/stat/traffic?period=month&accuracy=1&id=84013735&stateHash=6118ea8840ff3a002011a4c8

Создать новый отчёт по посещаемости:

- Отчёты -> Мои отчёты -> [Новый отчёт](img/20.ym-new-report.png)
- Убрать ненужные группировки, [тут](img/21.ym-grouping-1.png) и [тут](img/22.ym-grouping-2.png)
- Выбрать нужные [период и детализацию, отключить график](img/23.ym-settings.png)
- Почистить метрики: [открыть окно](img/24.ym-metrics.png), [удалить ненужные](img/25.ym-metrics.png).
- [Сохранить](img/26.ym-report-save.png) отчёт как "Посещение по целям"
- Пометить отчёт как [избранный](img/27.report-fav.png)

В отчёте отображаются базовые метрики по посещаемости [по всему счётчику](img/28.report-total.png)

- Визиты: Суммарное количество визитов 3
- Просмотры: Число просмотров страниц 31
- Посетители: Уникальных посетителей 3

[Выберите](img/29.report-choose-goal.png) одну цель и вам выведутся дополнительные 
колонки [по выбранной цели](img/30.report-by-goal.png). Нужные колонки:

- Достижения цели: **просмотры** страниц в выбранной группе
- Целевые визиты: **визиты** на страницы в выбранной группе
- Целевые посетители: **уникальные посетители** в выбранной группе

