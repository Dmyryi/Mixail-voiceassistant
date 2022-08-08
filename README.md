ТЕОРИЯ
========


> ## Медіа типи


* @media print {
  /* ... */
}



 
* @media screen and (min-width: 400px) {
  /* ... */
}


* all

>## Медіа-функції
* min-width і max-width
```css
/* Застосується, коли ширина в'юпорту більша за 900px */
@media (min-width: 900px) {
  body {
    background-color: green;
  }
}

/* Застосується, коли ширина в'юпорту менша за 600px */
@media (max-width: 600px) {
  body {
    background-color: yellow;
  }
}
```
![media-function](https://goit.global/textbooks/html-css-a7u5xv/v1/uk/img/lesson-15/min-max-queries.png)

>## Логічні оператори
```css
@media only|not media-type only|and|not (media-feature) {
  /*
    Набір CSS-правил, які потрібно застосувати до документа,
     якщо виконується умова перевірки медіатипу і виразу
  */
}
```

* ### Оператор `and`
```css
@media screen and (min-width: 400px) and (max-width: 800px) {
  body {
    background-color: red;
  }
}
```
![operator &](https://goit.global/textbooks/html-css-a7u5xv/v1/uk/img/lesson-15/query-segment.png)
* ### Оператор `,`
```css
@media (max-width: 600px), (min-width: 900px) {
  body {
    background-color: orange;
  }
}
```

![operator ,](https://goit.global/textbooks/html-css-a7u5xv/v1/uk/img/lesson-15/min-max-queries.png)

* ### Оператор `not`

>## Viewport
![viewport](https://goit.global/textbooks/html-css-a7u5xv/v1/uk/img/lesson-15/layout-viewport.jpg)

```html
<head>
  <!-- Інші мета-теги -->
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Мета-тег viewport важливий для адаптивних сторінок</title>
</head>
```
>## Типи верстки

* ### Responsive
* ### Adaptive

![type](https://goit.global/textbooks/html-css-a7u5xv/v1/uk/img/lesson-15/responsive-vs-adaptive.gif)

>## Стратегія Mobile First

![mobile-first](https://goit.global/textbooks/html-css-a7u5xv/v1/uk/img/lesson-15/mobile-first.webp)
* ### Mobile-first CSS
```css
.element {
  /* Базові стилі */
}

@media screen and (min-width: ширина-планшета) {
  .element {
    /* Стилі планшета */
  }
}

@media screen and (min-width: ширина-десктопа) {
  .element {
    /* Стилі десктопа */
  }
}
```
>Adaptive graphics
>>## Щільність пікселів
* Retina-дисплей (ретіна)
![retina](https://goit.global/textbooks/html-css-a7u5xv/v1/uk/img/lesson-16/retina.jpg)

>>## CSS-пікселі

![css-pixels](https://goit.global/textbooks/html-css-a7u5xv/v1/uk/img/lesson-16/css-pixels.png)

![css-retina](https://goit.global/textbooks/html-css-a7u5xv/v1/uk/img/lesson-16/css-pixel-scaling.png)
>>## Ретинізація графіки

![retiniztion](https://goit.global/textbooks/html-css-a7u5xv/v1/uk/img/lesson-16/bitmap-export.png)

>>## Респонсивне зображення

```css
img {
  display: block;
  max-width: 100%;
  height: auto;
}
```

![image](https://goit.global/textbooks/html-css-a7u5xv/v1/uk/img/lesson-16/basic-reposnsive-image.png)

>>## Респонсивні фонові зображення

```css
/* Базові стилі і 1x зображення */
.box {
  width: 480px;
  height: 320px;
  background-image: url('photo.png');
  background-size: 480px 320px;
}

/* Перевизначаємо шлях до 2x зображення,
    якщо щільність екрану мінімум 2 */
@media (min-device-pixel-ratio: 2),
  (min-resolution: 192dpi),
  (min-resolution: 2dppx) {
  .box {
    background-image: url('photo@2x.png');
  }
}
```
>>## Респонсивний елемент <img>
![responsive-img](https://goit.global/textbooks/html-css-a7u5xv/v1/uk/img/lesson-16/responsive-img-tag.png)
>## Атрибут `srcset`

```html
<img srcset="" src="" alt="" />
```

>>##  Дескриптор `x`

```html
<img
  srcset="photo.jpg 1x, photo@2x.jpg 2x"
  src="photo.jpg"
  alt="Опис зображення для усіх версій"
/>
```

>>## Дескриптор `w`
```html
<img
  srcset="photo-300.jpg 300w, photo-600.jpg 600w, photo-1200.jpg 1200w"
  src="photo-300.jpg"
  alt="Опис зображення для всіх версій"
/>
```
>>## Атрибут `sizes`

```html
<img
  srcset="photo-300.jpg 300w, photo-600.jpg 600w, photo-1200.jpg 1200w"
  sizes="(min-width: 900px) 600px, (min-width: 600px) 300px, 100vw"
  src="photo-300.jpg"
  alt="Опис зображення для всіх версій"
/>
```

>## Елемент `<picture>`

>>## Синтаксис

```html
<picture>
  <source srcset="photo.webp 1x, photo@2x.webp 2x" type="image/webp" />
  <source srcset="photo.jpg 1x, photo@2x.jpg 2x" type="image/jpeg" />
  <img src="photo.jpg" alt="Кіт" />
</picture>
```

>>## Кадрування `(art direction)`

```html
<!-- Для екранів ширше 600px буде завантажений photo-wide.jpg -->
<picture>
  <source srcset="photo-wide.jpg" media="(min-width: 600px)" />
  <img src="photo.jpg" alt="Фотографія" />
</picture>
```

# ПРАКТИКА
## container
## header
## image
## Continue
