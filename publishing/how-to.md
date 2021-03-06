Предварительные условия

1. Текстовый редактор.
1. Графический редактор для подготовки изображений. Например **Photoshop**.

:bulb: Не пользуйтесь `Notepad` или `Microsoft Word` для редактирования содержимого сайта!
Рекомендуется `Visual Studio Code` (**VSC**). Ссылка для скачивания [здесь](https://code.visualstudio.com/download).
Желательно дополнительно установить расширения для **VSC**: "YAML Language Support by Red Hat", "Markdown All in One", "markdownlint.
**VSC** облегчает редактирование Markdown и YAML, а также позволяет не пользоваться командной строкой при работе с системой контроля версий и удаленным репозиторием.  


Сначала загружаем самую свежую версию данных сайта из удаленного репозитория. Это необходимо сделать до начала каких-либо правок на локальном компьютере, чтобы избежать ручного разрешения конфликтов слияния версий разных пользователей. Если правка данных производится только одним пользователем и на одном компьютере, то это выполнять нет необходимости.

Правим данные на локальном компьютере, сохраняем результаты работы в локальный репозиторий и затем синхронизируем локальный репозиторий с удаленным.

GitHub сам отследит все изменения в удаленном репозитории, скомпилирует и опубликует обновленную версию сайта.

**Cхема процесса обновления сайта**

![Пошаговая схема процесса обновления сайта](../assets/images/git-workflow-actions-v2.svg)

1. Запустите Visual Studio Code
2. Откройте папку с данными - меню File -> Open Folder..., папка `[CONTENT_DIR]`.
3. Откройте Teminal: меню Teminal -> New Terminal
4. Получите последнюю версию данных из удаленного репозитория

   В окне Teminal выполните команду

   ```bush
   git pull
   ```

   Если правка данных производится только одним пользователем и на одном компьютере, то пункты 3 и 4 можно пропустить.
5. Отредактируйте и сохраните данные сайта.
6. Поместите измененные файлы в локальный репозиторий и выполните синхронизацию с удаленными репозиториями.

   Пункт меню `Terminal -> Run Build Task...` или одновременное нажатие клавиш `Crtl + Shift + B`.

   Запустится командный файл. Введите сообщение для commit-а о сделанных вами правках.


Синхронизация данных в удаленных репозиториях производится автоматически.

GitHub отследит эти измения, cкомпилирует и опубликует обновленный сайт на Netlify.

Сообщение об успехе или ошибке генерации сайта будет переслано в Telegram-канал.
