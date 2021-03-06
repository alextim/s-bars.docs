Папка: `[CONTENT_DIR]/data/locales`

| Что                | Подпапка        | Имя файла            | Комментарий
| ------------       | --------------- | -------------------  | -------------------
| Главное меню       | ./main-nav      | main-nav.uk.yaml     |
|                    |                 | main-nav.ru.yaml     |
| Навигация в футере | ./footer-nav    | footer-nav.uk.yaml   |
|                    |                 | footer-nav.ru.yaml   |
| Ссылки на соц.сети | ./social-links  | social-links.uk.yaml | Facebook, Instagram и тд
|                    |                 | social-links.ru.yaml |
| Адрес              | ./address       | address.uk.yaml      | Официальное название организации, почтовый адрес, подробное описание контактов
|                    |                 | address.ru.yaml      |
| Переводы           | ./translations  | translations.uk.yaml | Для внутреннего использования
|                    |                 | translations.ru.yaml |

## Навигация в футере

Список полей

|   Поле       | Описание
|---           |---
| to           | путь к странице без префикса языка, но со слешем в конце. Пример: `/contacts/`
| title        | название ссылки

## Главное меню

Список полей

|   Поле       | Описание
|---           |---
| to           | путь к странице без префикса языка, но со слешем в конце. Пример: `/contacts/`
| title        | название ссылки
| submenu      | составное поле, подменю c подпунктами **to** и **title**

:warning: Последовательность пуктов главного меню важна! Запрограммировано так, что первый пункт Главного меню будет **Услуги**, а второй **Типы объектов**.

Из подменю пункта **Услуги** создается список услуг для страницы `Услуги`, для сайдбара на странице "Пост" и на странице конкретной услуги.

Соответственно из подменю пункта **Типы объектов** создается список типов объектов для `Главной` страницы, для страницы `Типы объектов` и список типов объектов для сайдбара на странице конкретного типа объекта.

## Ссылки на социальные сети

Ссылки на профили в соц.сетях отображаются в футере сайта в виде иконок.

Список полей

|   Поле       | Описание
|---           |---
| to           | ссылка на ваш профиль в социальной сети
| title        | всплывающая подсказка
| code         | код соц.сети


При наведении курсора мыши на иконку выводится всплывающая подсказка (поле **title**).


:warning: Поле **код** используется для построения SEO и для вывода иконки.

Для добавления соц.сетей, отличных от Instagram и Facebook, нужен программист.


## Адрес

Содержимое этого файла используется на странице "Контакты" и SEO.

Поле **e-mail** в виде списка, разделитель элементов списка запятая `,`.



Поле **telephone** в виде списка цифровых значений, разделитель элементов списка запятая `,`.

:bulb: Номер телефона допускает только цифры, без плюса спереди, без пробелов, скобок и прочих символов.

Пример содержимого:

```yaml
name: Сніговий Барс
alternateName: Компанія «Сніговий Барс»
legalName: Промисловий альпінізм Сніговий Барс
description: На будь-якому з етапів виконання будівельного плану, клінінгових і ремонтних робіт послуги промислових альпіністів компанії «Сніговий Барс» будуть максимально вигідним для Вас рішенням


postalAddress:
  streetAddress:
    - Хмельницьке шосcе, 2а, оф.110
  addressLocality:  Вінниця
  addressRegion: Вінницька обл.
  postalCode: 21036
  # для структурированных данных, два символа ISO 3166-1 alpha-2
  addressCountry: UA
  # для вывода на странице Контакты
  addressCountryName: Україна

contactPoint:
  - name: Світлана Доляк
    description: Фарбування металоконструкцій, фасадів і т.д.
    # для структурированных данных
    contactType: customer service
    # для вывода на странице Контакты
    contactTypeName: відділ роботи з клієнтом
    telephone: [380965553092]
    email: [promalp.s.bars@gmail.com]
  - name: Андрій Карпенко
    description: Утеплення квартир
    # для структурированных данных
    contactType: customer service
    # для вывода на странице Контакты
    contactTypeName: клієнт-менеджер
    telephone: [380979705376, 380432573695]
    email: [andrey.karpenko7@gmail.com]
```

### Переводы

Переводы используются только в коде программы. Поэтому не предполагается их редактирование.

Если все же возникла такая потребность, то:

- Отредактируйте соответствующий `JSON` файл в папке `[CONTENT_DIR]/data/locales/translations/src/`.
- Зайдите в командную строку, перейдите в папку `[PROJECT_DIR]` и выполните команду `yarn trans`.
  Эта команда запустит javascript-скрипт, который преобразует файл c переводами из формата `JSON` в `YAML` (Вам потребуется предварительно установить на локальный компьютер **nodejs** и **yarn**).

  :bulb: Для автоматического обновления переводов во время `commit`-a потребуется дополнительно установить **husky** и **lint-staged**.
- выполните действия из раздела **[Публикация изменений](#публикация-изменений)**.
