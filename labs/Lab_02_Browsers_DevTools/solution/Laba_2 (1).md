##Лабораторная работа 2
###Инструменты разработчика в браузере
###Задание №1. Исследование заголовков и тела обычных запросов и их ответов.

- Request URL         - запрашиваемый URL, значение хота ресурса.
- Request Method      - GET-запрос используется для получения данных.
- Status Code         - код состояния.
- Remote Address      - удалённый адрес и IP адрес.
- Referrer Policy     - помогает предотвратить утечку данных на сайты, куда идут ссылки.
- content-type        - тип контента запрашиваемой страницы.
- cache-control       - задает инструкции кэширования запросов и ответов.
- cookie              - небольшие данные сохраняемые у пользователя
- user-agent          - часть текствого запроса, в котором информация веб-приложения сообщается сайту.
- referer             - позволяет узнать откуда был отправлен запрос.

Порт подключения - числовой идентификатор, который используется компьютерами и устройствами для определения,
к какому конкретному приложению или службе следует направить входящую или исходящую информацию.

Заголовки разделены от `<h1>` до `<h6>` и влияет на размер текста и отступ после него.

Заголовки используются для поиска информаии.

Заголовок `<h1>` самый главный и большой.

Тело ответа - информация, которую зарпашивает клиент. Где код ответа - признак успешности выполнения запроса.
- Стартовая строка (`start line`) — используется для описания версии используемого протокола и другой информации — вроде запрашиваемого ресурса или кода ответа.
- HTTP-заголовки (HTTP Headers) — несколько строчек текста в определенном формате, которые либо уточняют запрос, либо описывают содержимое тела сообщения.
- Пустая строка, которая сообщает, что все метаданные для конкретного запроса или ответа были отправлены.
- Опциональное тело сообщения, которое содержит данные, связанные с запросом, либо документ, передаваемый в  ответе.

###Задание №2. Исследование указывающих ответов сервера.

Сделав запрос `http://rgups.ru/` мой адрес изменился на `https://rgups.ru`.
Это означает, что передаваемые данные идут по защищённому протоколу.

Изменился порт в заголовке Remote Address, c `80` на `443`.

Первоначальный Status Code: `301 Moved Permanently`, при переходе Status Code: `200 OK`.

### Задание №3. Исследование получения и передачи cookie.

Повторив запрос на `https://ya.ru/` увидел, что заголовок `Set-Cookie` с сервера даёт клиенту указание сохранить куки.

```html
HTTP/1.0 200 OK
Content-type: text/html
Set-Cookie: yummy_cookie=choco
Set-Cookie: tasty_cookie=strawberry
```

Флаги Cookie: 
- `Name` - это ключ для куки, её имя.
- `Value` - это значение куки.
- `Domain` - это часть адреса сайта, которая содержит домен на который cookie сервера отправляет файл.
- `Path` - это путь к файлу.
- `Expires` - необходим для определения срока жизни токена.
- `Same Path` - показывает условия в которых cookie может быть отправлен на межсайтовые запросы.

Для того, чтобы просмотреть все cookie связанные с текущим (просматриваемым) 
сайтом необходимо:  
- Нажать сочетание клавиш Ctrl + Shift + I(или F12) 
- Перейти во вкладку Application и Storage - Cookies  

Назначение cookie в том, что это текстовый файл с различной информацией о пользователе,
который сайты сохраняют на компьтере, чтобы сайт не видел одного и того же пользователя 
как впервый раз. Следовательно знал ваш язык, ваш аккаунт и ваши предпочтения на сайте.

### Задание №4. Исследование построения документов и сопутствующих запросов.

DOM (Document Object Model, Модель объектов документа) - это структура представления веб-страницы
или документа в виде иерархического дерева объектов.

Простыми словами, DOM - это способ организации и внутреннего представления веб-страницы, который
позволяет программам и скриптам взаимодействовать с элементами документа.

Да, итоговый документ, который отображается веб-браузером, может отличаться от тела ответа, полученного от сервера.

Это может произойти из-за:
- Обработки на стороне клиента: Веб-браузер может выполнить дополнительные шаги обработки
полученного контента перед его отображением.
- Кэширования: Если у браузера есть сохраненная копия страницы в кеше, то он может использовать
эту версию вместо повторной загрузки с сервера. В результате, содержимое страницы может быть разным в
зависимости от того, когда она была загружена и сохранена в кеше.
- Динамического содержимого: Некоторые части веб-страницы могут быть созданы или изменены с помощью JavaScript или 
других технологий на стороне клиента.

Даже если сделать всего один запрос в списке будет большое количество запросов и ответов потому, что
сеть подгружает всё по частям. Браузер подгружает файлы для получения информации из сети.

Это могут быть различные картинки формата `.png`, скрипты `.script`, шрифты `font` и так далее.

### Задание №5. Определение параметров запроса.

Чтобы получить желаемый резульат я выполнил get-запрос
`https://www.rgups.ru/ajax/schedule.php?action=timetable&fac-id=1&course-id=3&group-id=26335&edu-type=internal`
Часть URL идущая после знака "?" говорит серверу какие данные необходимо получить.
 Данные, которые я получил выполнив запрос: `action: timetable fac-id: 1 course-id: 3 group-id: 26335 edu-type: internal`

```shell
– в режиме видеоконференцсвязи
Понедельник (сегодня)
1	8.20-9.50	обе недели	Военная подготовка ()	..	
2	10.05-11.35	обе недели	Военная подготовка ()	..	
3	12.05-13.35	обе недели	Военная подготовка ()	..	
4	13.50-15.20	обе недели	Военная подготовка ()	..	
5	15.30-17.00	обе недели	Военная подготовка ()	..	
Вторник (завтра)
2	10.05-11.35	обе недели	Визуальное программирование и графические интерфейсы (ЛЕК)	ВЕДЕРНИКОВА О.Г.	Г313
3	12.05-13.35	обе недели	Схемотехника информационных систем (ЛАБ)	КРАВЧЕНКО И.Ф. [2]	Г302
Схемотехника информационных систем (ЛАБ)	СОКИРКА А.Д. [1]	Г303
4	13.50-15.20	обе недели	Веб-программирование (ЛАБ)	КАПКАЕВ А.А. [1]	Г315
Веб-программирование (ЛАБ)	ХУСАИНОВ В.Р. [2]	Г315
5	15.30-17.00	обе недели	Базы данных и прикладное программирование (ЛАБ)	ЗЫРЯНКИНА К.Э. [1]	Г315
Базы данных и прикладное программирование (ЛАБ)	ГАЛЬЦЕВА А.А. [2]	Г315
Среда
1	8.20-9.50	обе недели	Визуальное программирование и графические интерфейсы (ЛАБ)	ВЕДЕРНИКОВА О.Г. [1]	Д407
Визуальное программирование и графические интерфейсы (ЛАБ)	ОЛЬГЕЙЗЕР И.А. [2]	Д410
2	10.05-11.35	обе недели	Экономика и менеджмент (ПРАК)	ТИМЧЕНКО О.В.	А420
3	12.05-13.35	обе недели	Базы данных и прикладное программирование (ЛЕК)	ИГНАТЬЕВА О.В.	Г313
4	13.50-15.20	обе недели	Схемотехника информационных систем (ЛЕК)	ЛЯЩЕНКО А.М.	Г313
Четверг
1	8.20-9.50	над чертой	—		
под чертой	Системное программное обеспечение информационных систем (ЛАБ)	ДЕМИЧЕВ А.А. [1]	Д407
2	10.05-11.35	обе недели	Экономика и менеджмент (ЛЕК)	КАЛАШНИКОВ И.А.	С204
3	12.05-13.35	над чертой	Безопасность жизнедеятельности (ЛЕК)	ПЕРЕВЕРЗЕВ И.Г.	М215
под чертой	Безопасность жизнедеятельности (ЛАБ)	ВОРОБИНСКАЯ Л.И. [2]	М156
Безопасность жизнедеятельности (ЛАБ)	ЯИЦКОВА Н.М. [1]	М153
4	13.50-15.20	над чертой	Безопасность жизнедеятельности (ПРАК)	ПЕРЕВЕРЗЕВ И.Г.	М231
под чертой	—		
Пятница
1	8.20-9.50	над чертой	Системное программное обеспечение информационных систем (ПРАК)	ЖУКОВ В.В.	Д407
под чертой	Системное программное обеспечение информационных систем (ЛАБ)	НИКИТЧЕНКО С.Л. [2]	Д406
2	10.05-11.35	обе недели	Системное программное обеспечение информационных систем (ЛЕК)	ЖУКОВ В.В.	Г313
3	12.05-13.35	обе недели	Веб-программирование (ЛЕК)	КАПКАЕВ А.А.	Г313
```