# Best frontend practices

### Дизайн 

#### Если понадобится стилизовать форму или какой-нибудь элемент самой
1. [Статья](https://habrahabr.ru/company/cloud4y/blog/349826/)

#### Используйте меньшее количество границ 

Когда нужно обозначить разделение между двумя элементами, лучше избежать добавление бордеров, их использование в слишком большом количестве может перегрузить дизайн деталями и создать чувство загроможденности. Есть и другие способы:  
* box-shadow 
* Используйте два разных цвета фона
* Добавьте дополнительный интерва

#### Не увеличивайте значки, которые должны быть маленькими 

Иконки с малым количествой элементов лучше не увеличивать, отсутсвие деталий ухудшает их восприятие, если размер больше задуманного

#### Используйте акцент для границы, чтобы добавить цвет в безликий дизайн

#### Не каждая кнопка нуждается в цветном фоне

### Текст/Шрифты
* [Онлайн типографов](https://www.artlebedev.ru/typograf/) - для оформление текста, чтобы не расставлять ручками неразрывные пробелы и т.п.  
* Оптимальная высота строки (line-height) 1.4 — 1.8 от размера шрифта.  
* [Конвертор шрифтов](https://onlinefontconverter.com/)  
* На айфоне бывает неконтролируемый резайз шрифтов, надо поробовать добавить: `-webkit-text-size-adjust: none;`  
* Заметка на будующее - [доклад от Юлии Бухваловой](https://wsd.events/2019-04-13/ascii-emoji/) про кастомные шрифты


### Изображения 
* Инфо по тегу `<picture>` [с кучей примеров](https://frontender.info/responsive-images/)
* Сделать одноцветную [png](http://png-pixel.com/)
* Плагин `postcss-inline-svg` который при сборке может менять фон SVG и его инлайнить, [подробнее](https://css-tricks.com/images-in-postcss/#article-header-id-5)
* [картинки-превью](https://stackoverflow.com/questions/2068344/how-do-i-get-a-youtube-video-thumbnail-from-the-youtube-api) для видео на YT 
* [Иконки](https://icons8.com/), в частности [svg-прелодеры](https://icons8.com/preloaders/)
* Ленивая загрузка изображений, в данной случае фонового, с помощью [Intersection Observer API](https://codepen.io/imagekit_io/pen/RBXVrW/). [Документация](https://developer.mozilla.org/ru/docs/Web/API/Intersection_Observer_API) с примерами. [Поддержка](https://caniuse.com/#search=Intersection%20Observer%20API) хорошая, в IE конечно нет.


### Видео
* [документация гугла](https://developers.google.com/web/updates/2017/09/autoplay-policy-changes) . 
**ВАЖНО** не забыть атрибут `muted` на `<video>` с `autoplay`  

* атрибут `playsinline` у `<video>` не позволяет ему воспроизводиться в полноэкранном режиме на iPhone



### Верстка элементов 
* Верстка простых элементов [круг, квадрат, треугольник](https://codepen.io/miocene/pen/LOoGpr)
* `<select>` [кроссбраузерная стилизация select ](http://kate-land.net/html-css/item/336-cross-browser-styling-of-select-on-pure-css)  

```css
select {
    width: 100%;
    border: 0;
    height: 3.7rem;
    line-height: 1em;
    /*text-indent: .01px;*/
    /*text-overflow: '';*/
    appearance: none;
    -webkit-appearance: none;
    -moz-appearance: none; 
    -moz-outline: none;
    padding-left: 5%;
    font-weight: bold;
    outline: none !important;
    color: black;
}
```
Возможно нужен не селект на самом деле, есть еще [datalist](https://developer.mozilla.org/ru/docs/Web/HTML/Element/datalist) и [optgroup](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/optgroup)

* `clip` [статья для понимания](http://css.manual.ru/properties/clip)
* Для `input[type='number']`   
```css
&:-moz-focusring {
    outline: none;
}

&::-webkit-outer-spin-button,
&::-webkit-inner-spin-button {
    -webkit-appearance: none;
    margin: 0;
}
```
* Удобный [сайт](http://yoksel.github.io/flex-cheatsheet/#display) для понимая `flex` 
* [Треугольники на css](https://css-tricks.com/snippets/css/css-triangle/) 
* [Градиент при избыточной прокрутке](http://plnkr.co/edit/agPbF2XDrjyiTWYpovOl?p=preview)  
* Старое-доброе позиционирование по ценру
```css
.divInCenter {
    width: 300px; /* жестко задана ширина */
    position: absolute;
    left: 50%;
    margin-left: -150px; /* отрицательный отступ равный 1/2 ширины (width) позиционируемого блока */ 
}
```
* Пульсирующий волны [от круга](https://codepen.io/davidmellul/pen/BVQrrg)
* [Подергивание элемента](https://plnkr.co/edit/cuyRYHG8KpVIzbdO2Gqf?p=preview) 
* Анимации для [гамбургер-меню](https://codepen.io/ainalem/details/LJYRxz/)
* Контентная картинка, [как бэкграунд-cover через svg](https://next.plnkr.co/plunk/3o9fcVQsmtbLwUFlKv8Y) + [статья](https://www.sarasoueidan.com/blog/svg-object-fit/), но в таком способе использования (через svg) приоритет загрузки у картинки всегда будет LOW
* truncate, [статья](https://css-tricks.com/almanac/properties/l/line-clamp/). [Truncate](https://codepen.io/anastasiyadev/pen/QWWBMbx) для select
```css
.text-block {
    overflow: hidden;
    height: 40px;
    display: -webkit-box;
    -webkit-line-clamp: 3;
    -webkit-box-orient: vertical; 
}
```
* [Паттерны для таблиц с логикой](https://www.smashingmagazine.com/2019/01/table-design-patterns-web/)
* `inputmode` - атрибут для `input` и `textarea` указывающий какую клаву на мобилке открыть, крутая и удобная штука, но поддержка в линейке iphone начия от 6го, а на рынке еще много 5к. [Сататья про inputmode](https://css-tricks.com/everything-you-ever-wanted-to-know-about-inputmode/) 
* Повернутый текст
```css
.rotated {
    writing-mode: tb-rl;
    transform: rotate(-180deg);
}
```
* Управляет доступом к заголовку Referer
```html
<a href="https://some-site.com"
   referrerpolicy="no-referrer">
   External Resource
</a>
```
* Можно указать в ссылке на почту так же тему письма, кого поставить в копию и др.
```html
<a href="mailto:mefody@yandex-team.ru
      ?cc=dark.mefody@yandex.ru,n.a.dubko@gmail.com
      &bcc=n.a.dubko@gmail.com
      &subject=I%20Love%20Frontend%202020
      &body=Хочу%20выступить">
```
* Для ссылки, открывающейся в новом окне хорошо бы это показать, например, иконка перед текстом
```css
a[target="_blank"]::before {
    content: url('path-to-icon.svg');
}
```
* Задержка после таба по устройству - **300ms**, чтобы его исключить - `touch-action: manipulation`. Не поддерживается только в сафари
* Библиотека для фокуса на элементах - [flying-focus](https://github.com/NV/flying-focus)
* `text-decoration-skip-ink: auto` делает красовое подчеркивание. Работает в хром и FF
* Галочка на CSS:
```
content: '';
position: absolute;
left: 5px;
top: 5px;
width: 5px;
height: 9px;
border: solid @white;
border-width: 0 2px 2px 0;
transform: rotate(45deg);
```

### Письма
* [Кнопки для писем](https://buttons.cm/)
* [Мапинг картинок](https://www.image-map.net/)
* [Поддержка css-свойств и не только](https://www.campaignmonitor.com/css/color-background/background-clip/)  
* [Поддержка медиа-выражений в письмах](https://github.com/AnastasiyaDev/best-front-practices/blob/master/images/media-in-emails.jpg) на февраль 2018 года
* [Таймер](https://www.sendtric.com/)
* [Какие шрифты использовать](https://www.unisender.com/ru/blog/sovety/kakie-shrifty-ispolzovat-v-rassylke)
```
Без засечек:
*   Arial
*   Arial Black
*   Tahoma
*   Trebuchet MS
*   Verdana
* Lucida Console 

С засечками:
*   Courier
*   Courier New
*   Georgia
*   Times
*   Times New Roman
```


### Полезные плагины для браузера
* Page Ruler
* FireShot
* PerfectPixel by WellDoneCode
* Tampermonkey
* Siteimprove Accessibility Checker
* [Switcheroo Redirector](https://chrome.google.com/webstore/detail/switcheroo-redirector/cnmciclhnghalnpfhhleggldniplelbg/related?hl=ru)


### Полезные плагины(на JS/jQuery)
* Счетчик - [countUp.js](https://inorganik.github.io/countUp.js/)
* Проверка наличия элемента во вьюпорте - [jquery-visible](https://github.com/customd/jquery-visible)
* Анимированое появление элементов, плагин платный - [wowjs](https://github.com/matthieua/WOW)
* Параллакс для фона - [jquery-parallax.js](http://pixelcog.github.io/parallax.js/)
* Параллакс для фиксированных блоков на странице - [rellax](https://www.npmjs.com/package/relax)
* Слайдер 3D, возможностей не хватает и работает как-то костыльно, но бесплатен и уже используется на килзе и лореале - [jQuery Rondell](https://www.jqueryscript.net/demo/Highly-Customizable-Carousel-Plugin-For-jQuery-rondell/examples/options.html) - стоит поискать аналог
* flipclock — вылезла проблема, не работает корректно, если стоит больше 2х недель
```javascript
var date    = new Date(2018, 2, 31, 24),
                now     = new Date(),
                diff    = (date.getTime() / 1000) - (now.getTime() / 1000),
                seconds = (diff > 0) ? diff : 0,
                clock;

            clock = new FlipClock(this.$timer, {
                clockFace: 'DailyCounter',
                countdown: true,
                language: 'ru-ru',
                showSeconds: true,
                autoStart: false
            });

            clock.setTime(seconds);
            clock.start();
```
* [countdownjs](http://countdownjs.org/demo.html) — нашла как альтернативу **flipclock**, документация так себе, но разобраться можно
```javascript
var date = new Date(2020, 0, 15, 0, 0);

countdown(
    date,
    function(ts) {
        document.getElementById('mcaTimer').innerHTML = ts.toHTML('strong');
    },
    countdown.DAYS|countdown.HOURS|countdown.MINUTES,
    countdown.setLabels(
        ' milliseconde| секунда| минута| час| день| semaine| mois| année| décennie| siècle| millénaire',
        ' millisecondes| секунд| минут| часов| дней| semaines| mois| années| décennies| siècles| millénaires',
        ' ',
        ' ',
        ' ',
        function(n){return '<span class="mca-2018-timer__numeric">' + n + '</span><br>'; }
    )
);
```


### Сслыки
* Микроразметка, пояснения [от яндекс](https://yandex.ru/support/webmaster/schema-org/what-is-schema-org.xml), [schema.org](http://schema.org/docs/gs.html)  
* Установка [NPM глобально](https://docs.npmjs.com/getting-started/fixing-npm-permissions) - на убунте нормально не работает
* https://lawsofux.com/
* Полезная [статья](https://bespoyasov.ru/front-not-pain/#progress) про фронтэнд разработку
* [sessionStorage](https://developer.mozilla.org/ru/docs/Web/API/Window/sessionStorage)
* Ресурс для изучения [git](https://learngitbranching.js.org/), еще не тыкала, но выглядит удобно
* Статья про бесплатные [конструкторы сайтов](https://tproger.ru/digest/website-builders-review/)
* [keyframes.app](https://keyframes.app/)
* [cssgrid-generator](https://cssgrid-generator.netlify.com/)

TODO @me
- [ ] Сделать пример по [видео](https://www.youtube.com/watch?v=C9EWifQ5xqA)
- [ ] Пополнить список плагинов
