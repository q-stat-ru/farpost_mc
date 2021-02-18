# farpost_mc
Файлы для внутреннего мастер-класса по Power BI для компании Farpost

#### Скачать десктопную версию (только для Windows)
https://www.microsoft.com/en-us/download/details.aspx?id=58494

## Дисклеймер
Все данные представленные в данном репозитории отличаются от реальных, но на выполнение задания это никак не повлияет.

## Полезные ссылки
Справочник по Power Query - https://docs.microsoft.com/ru-ru/powerquery-m/power-query-m-function-reference
Справочник по DAX - https://docs.microsoft.com/ru-ru/previous-versions/sql/sql-server-2016/ee634396(v=sql.130)
Русскоязычное сообщество по Power BI
* Facebook - https://www.facebook.com/groups/powerBiForever
* Телеграм - https://t.me/PBI_Rus
https://powerbirussia.ru/category/tutorials-and-manuals/
Неплохой русскоязычный сайт про Power BI - https://powerbirussia.ru/category/tutorials-and-manuals/
Мой сайт про аналитику и Power BI - https://q-stat.ru/

## Задания
Данные для заданий разбиты по папкам

## Урок 1. 
### Презентация
https://docs.google.com/presentation/d/1kUxG8pM4Eo2MKxlk3Bg_s3pRLEM9j-qss8ENEPoEiU8/edit?usp=sharing

### Видео-запись урока
_Появится позже_

### Проблема
Мы ведем множество различных соцсетей. Но смотреть статистику мы можем только в каждой сети отдельно, а мы бы хотели иметь возможность сравнивать между собой соцсети.
### Задание
Разработать систему на основе выгрузки статистики из разных социальных сетей, чтобы получить наглядное представление полезности каждой социальной сети в сравнении с другими. 

### Источники данных
posts.csv - информация о постах из различных соцсетей

post_stat.csv - статистика в разрезе постов

Календарь - https://docs.google.com/spreadsheets/d/e/2PACX-1vQolps9D_y0dxeVACI4X0asUTWhGcsbYae5nkqZNBmzq-sqEBrW-SUm3Q8JuaVG9RpdUqHv9fiDExjH/pub?output=csv

### Ход выполнения
1. Загрузить данные в отчет
2. Подгрузить справочники
3. Создать недостающие таблицы (таблица с именами соцсетей)
4. Связать модель
5. Создать таблицу как простейшую визуализацию и проверить что всё ок
6. Создать меру Engagement = SUM(post_stat[likes]) + SUM(post_stat[comments]) + SUM(post_stat[reposts]) + SUM(post_stat[clicksToLink])
7. Создать меру ER = [_Engagement]/SUM(post_stat[reach])

### Домашнее задание
1) Создать меры Reach/Post, Views/Post
2) Сделать отчет, который бы показал Топ5 постов с различными фильтрами
3) Найти зависимости между различными показателями
4) Вычленить хештеги из текста, чтобы сделать возможным фильтрацию по тегам
