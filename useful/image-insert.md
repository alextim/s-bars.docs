Предполагается, что изображения находятся рядом с самим документом в подпапке `./images`.

Ширина генерируемых из Markdown изображений настраивается в файле `gatsby-config.js`, константа **maxWidth**.

```js
          {
            resolve: 'gatsby-remark-images',
            options: {
              /**
               * 1280px - current layout width
               * 896px - content column
               * for 100% width
               *
               */
              maxWidth: 896,
              quality: 50,
            },
```

:bulb: Чтобы изображение занимало всю длину колонки в материалах "Услуга", "Тип объекта" и "Пост" надо подготовить исходный файл с шириной не меньше `896px`.

Если в теле страницы (markdown) исходное изображение шириной меньше 896px, то оно выравнивается по центру с отступами по краям.


Согласно требований Google минимальная ширина изображения должна быть не меньше 696px. Иначе она не попадет в **Google Images**. Подробнее [здесь](https://developers.google.com/search/docs/advanced/guidelines/google-images?hl=ru).


:bulb: Для быстродействия сайта, сокращения времени построения сайта (300мин бесплатно от Netlif) и SEO **всегда** оптимизируйте ваши изображения в графическом редакторе до публикаци на сайте, устанавливайте их размер согласно рекомендаций по документации и настраивайте качество.

!> Не забывайте указывать ALT текст для изображений (*длина до 125 символов*). Изображения без ALT не будут найдены поисковым роботом!

Текст для всплывающей подсказки используется в **Google Images**, поэтому его также желательно указывать.


Вы можете вставлять изображения в тело страницы при помощи синтаксиса Markdown или тегов HTML.

Вариант с тегами HTML подходит, если вам нужно задать особый формат вывода или вы не хотите стандартной обработки изображенией генератором статических сайтов.

<!-- tabs:start -->

#### **Синтаксис Markdown**

:heavy_check_mark: хорошо:

```md
![Альтернативный текст изображения](./images/your-image.jpg "Необязательный текст для всплывающей подсказки")

![Альтернативный текст изображения](./images/your-image.jpg)
```

:x: плохо:

```md
![](./images/your-image.jpg)
```

#### **HTML, без обработки**

Поместите изображение в папку `[PROJECT_DIR]/static/assets/images` отдельно от документа.

:heavy_check_mark: хорошо:

```html
<img 
  src="assets/images/your-image.jpg" 
  alt="Альтернативный текст изображения" 
  title="Необязательный текст всплывающей подсказки"
/>

<img src="assets/images/your-image.jpg" alt="Альтернативный текст изображения"/>
```

:x: плохо:

```html

<img src="assets/images/your-image.jpg" alt="" />
```

#### **HTML, особые стили**

Сгенерированный пример оформления можно посмотреть [здесь](https://igrig.netlify.app/blog-post-sample/).

Исходный файл примера [здесь](https://raw.githubusercontent.com/alextim/igrig.content/main/blog/posts/blog-post-sample/index.en.md).

Список встроенных классов

|  Имя класса                  | Десктоп                      | Мобильный
| ---                          | ---                          | ---  
|  left                        | Плывет влево (float: left)   | float: none
|                              | Отступ справа и снизу        | Отступ снизу
|  right                       | Плывет вправо (float: right) | float: none
|                              | Отступ слева и снизу         | Отступ снизу
|  clearfix                    | Сброс плавания               |
|  w-10                        | Ширина 10%                   | Ширина 100%
|  w-20                        | Ширина 20%                   | Ширина 100%
|  w-30                        | Ширина 30%                   | Ширина 100%
|  w-40                        | Ширина 40%                   | Ширина 100%
|  w-50                        | Ширина 50%                   | Ширина 100%
|  w-60                        | Ширина 60%                   | Ширина 100%
|  w-70                        | Ширина 70%                   | Ширина 100%
|  w-80                        | Ширина 80%                   | Ширина 100%
|  w-90                        | Ширина 90%                   | Ширина 100%
|  grid-2                      | 2 колонки                    | 1 колонка
|  grid-3                      | 3 колонки                    | 1 колонка

<!-- tabs:end -->