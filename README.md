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


### Изображения 

* Инфо по тегу `<picture>` [с кучей примеров](https://frontender.info/responsive-images/)
* Сделать одноцветную [png](http://png-pixel.com/)
* Плагин `postcss-inline-svg` который при сборке может менять фон SVG и его инлайнить, [подробнее](https://css-tricks.com/images-in-postcss/#article-header-id-5)
* [картинки-превью](https://stackoverflow.com/questions/2068344/how-do-i-get-a-youtube-video-thumbnail-from-the-youtube-api) для видео на YT 

### Верстка элементов 
* `<select>` [кроссбраузерная стилизация select ](http://kate-land.net/html-css/item/336-cross-browser-styling-of-select-on-pure-css)  

```
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
* `clip` [статья для понимания](http://css.manual.ru/properties/clip)
* Для `input[type='number']`   
```
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
* Можно проверить [поддержку css-свойств и не только](https://www.campaignmonitor.com/css/color-background/background-clip/)  * [Треугольники на css](https://css-tricks.com/snippets/css/css-triangle/) 
* [Градиент при избыточной прокрутке](http://plnkr.co/edit/agPbF2XDrjyiTWYpovOl?p=preview)  
* [Поддержка медиа-выражений в письмах](https://github.com/AnastasiyaDev/best-front-practices/blob/master/images/media-in-emails.jpg) на февраль 2018 года

### Полезные плагины для браузера
* Page Ruler
* FireShot
* PerfectPixel by WellDoneCode
* Tampermonkey

### Полезные плагины(на JS/jQuery)
* Счетчик - [countUp.js](https://inorganik.github.io/countUp.js/)


### Сслыки
* Микроразметка, пояснения [от яндекс](https://yandex.ru/support/webmaster/schema-org/what-is-schema-org.xml), [schema.org](http://schema.org/docs/gs.html)  
* Установка [NPM глобально](https://docs.npmjs.com/getting-started/fixing-npm-permissions) - на убунте нормально не работает
* https://lawsofux.com/
* Полезная [статья](https://bespoyasov.ru/front-not-pain/#progress) про фронтэнд разработку
* [sessionStorage](https://developer.mozilla.org/ru/docs/Web/API/Window/sessionStorage)
