# farpost_mc
Файлы для внутреннего мастер-класса по Power BI для компании Farpost

#### Скачать десктопную версию (только для Windows)
https://www.microsoft.com/en-us/download/details.aspx?id=58494

## Дисклеймер
Все данные представленные в данном репозитории отличаются от реальных, но на выполнение задания это никак не повлияет.

## Полезные ссылки
Справочник по Power Query - https://docs.microsoft.com/ru-ru/powerquery-m/power-query-m-function-reference

Справочник по DAX - https://docs.microsoft.com/ru-ru/previous-versions/sql/sql-server-2016/ee634396(v=sql.130)

Русскоязычное сообщество по Power BI:
* Facebook - https://www.facebook.com/groups/powerBiForever
* Телеграм - https://t.me/PBI_Rus

Неплохой русскоязычный сайт про Power BI - https://powerbirussia.ru/category/tutorials-and-manuals/

Мой сайт про аналитику и Power BI - https://q-stat.ru/

## Задания
Данные для заданий разбиты по папкам

# Урок 1. 
### Презентация
https://docs.google.com/presentation/d/1kUxG8pM4Eo2MKxlk3Bg_s3pRLEM9j-qss8ENEPoEiU8/edit?usp=sharing

### Видео-запись урока
https://zoom.us/rec/share/FAWWMJMcLG2qLmyB5nJaDcj5ACDSDW0ZjWY-udO9g41FEn7Z-cg4w1eZWnFZhDJY.3bVD_GTD8cU0J9FC 
(Код доступа: Leuy*f77) 

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

# Урок 2. 
### Презентация
https://docs.google.com/presentation/d/15-y79DXYX5xHIMvDxDEHdic-xTjbczVTg4Ej8exMes0/edit?usp=sharing

### Видео-запись урока
https://zoom.us/rec/share/KK1D84Ngqk59i_B7cWO1YkaEY68RlBMzC4tTfMjWasJlSw3Nob5AKyeEXYrzAG0.u0oysGk3y2G0S-UE 
(Код доступа: J^uc6XB*)

### Проблема
Мы имеем данные полученные из API различных систем, а также выгрузки из бухгалтерской программы. 
### Задание
Подготовить данные к анализу.

### Источники данных
dump_vk_post.csv - данные о постах из ВКонтакте

dump_fb_post.csv - данные о постах из Facebook

dump_ig_post.csv - данные о постах из Instagram

dump_ok_post.csv - данные о постах из Одноклассников

dump_vk_post_stat.csv - данные о статистике постов из ВКонтакте

dump_fb_post_stat.csv - данные о статистике постов из Facebook

dump_ig_post_stat.csv - данные о статистике постов из Instagram

dump_ok_post_stat.csv - данные о статистике постов из Одноклассников

system-cost.xlsx - выгрузка из бухгалтерской программы с данными о тратах на соцсети в разрезе месяцев

### Ход выполнения
1) Выгружаем данные по постам, преобразуем, объединяем в одну таблицу posts
2) Добавляем дополнительные столбцы в таблицу posts
3) Выгружаем данные по статистике постов, преобразуем, объединяем в одну таблицу posts-stat
4) Присоединяем таблицу posts-stat к таблице posts
5) Выгружаем данные по таблице system-cost, преобразуем

#### Python-скрипт для выбора ссылок
dataset['link'] = dataset['text'].str.findall(r'https\:\/\/[A-Za-z0-9\/\.]+')

### Домашнее задание
1) Добавить данные по одноклассникам.
2) Добавить неучтенные хештеги.
3) Добавить недостающую таблицу справочник, чтобы связать posts и system-cost.
4) *Использовать параметр _dir, для путей к файлам (см. План урока.docx) и sample.pbix, как уже готовый вариант*



# Урок 3. 
### Презентация
https://docs.google.com/presentation/d/1GOXAZQ_b-HNsyI7E-AbIobh-7A9uA067NWX889ugKwg/edit?usp=sharing

### Видео-запись урока
https://zoom.us/rec/share/lAMS8TV8czYeyUaNH12RIOyICFn16Sqv3kmpW6gBCFqKi8og86CoyN_3-9atWI8v.ZGrZbWxjF1OjkUI_v (Код доступа: 5tG^U?SZ) 

### Проблема
Мы имеем все нужные данные для анализа, но в таком виде с ними работать не удобно.
### Задание
Подготовить данные к анализу. Создать модель

### Источники данных
bloggerList.csv - таблица блоггеров

data.csv - таблица данных

### Ход выполнения
1) Знакомимся с теми данными, которые у нас есть
2) Приводим данные к правильному виду
3) Связываем таблицы в модель

### Домашнее задание
Привести к правильной модели данные из второго урока


# Урок 4. 
### Презентация
https://docs.google.com/presentation/d/1foQ4sStibegKUpOLrlOjoeqTkMkyw_2CwgcYKj_lhys/edit?usp=sharing

### Видео-запись урока
https://zoom.us/rec/share/Qrm590B1z1QlAMkPnkyriLVzw5grSejhn9lPth-Ot1dEodICfljZoggIU0K8DWEL.piD9eZHOaPHQuR8K (Код доступа: +^q1a$h. )

### Проблема
Мы имеем несколько различных наборов данных, но смотреть на них только в табличном виде неудобно.
### Задание
Необходимо построить визуализации разного типа, лучше всего подходящие для каждого набора данных.

### Источники данных
sample_empty.pbix - пустой файл для работы
sample.pbix - готовый файл

### Ход выполнения
*ход выполнения подробно расписан в файле План урока.docx*
1) Card + Multi-row Card + KPI
2) Table + Matrix
3) Filter (Slicer)
4) Pie + Donut + Sunburst
5) Tooltip
6) Line + Area + Stacked Area Charts
7) Column + Bar Charts
8) Scatter chart
9) Custom charts - Histogram
10) Filled map

### Домашнее задание
1) Попробовать различные визуализации на материалах 3-го урока
2) Попробовать различные кастомные визуализации
