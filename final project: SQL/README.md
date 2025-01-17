# Статус проекта
`Завершен`

# Финальный проект: SQL

**Запрос на исследование**

Коронавирус застал мир врасплох, изменив привычный порядок вещей. В свободное время жители городов больше не выходят на улицу, не посещают кафе и торговые центры. Зато стало больше времени для книг. Это заметили стартаперы — и бросились создавать приложения для тех, кто любит читать.
Ваша компания решила быть на волне и купила крупный сервис для чтения книг по подписке. Ваша первая задача как аналитика — проанализировать базу данных. В ней — информация о книгах, издательствах, авторах, а также пользовательские обзоры книг. Эти данные помогут сформулировать ценностное предложение для нового продукта.

**Задачи исследования**
- Посчитайте, сколько книг вышло после 1 января 2000 года;
- Для каждой книги посчитайте количество обзоров и среднюю оценку;
- Определите издательство, которое выпустило наибольшее число книг толще 50 страниц — так вы исключите из анализа брошюры;
- Определите автора с самой высокой средней оценкой книг — учитывайте только книги с 50 и более оценками;
- Посчитайте среднее количество обзоров от пользователей, которые поставили больше 50 оценок.

## Описание данных

**Таблица `books`** содержит данные о книгах:

    book_id — идентификатор книги;
    author_id — идентификатор автора;
    title — название книги;
    num_pages — количество страниц;
    publication_date — дата публикации книги;
    publisher_id — идентификатор издателя.

**Таблица `authors`** содержит данные об авторах:

    author_id — идентификатор автора;
    author — имя автора.

**Таблица `publishers`** содержит данные об издательствах:

    publisher_id — идентификатор издательства;
    publisher — название издательства;

**Таблица `ratings`** содержит данные о пользовательских оценках книг:

    rating_id — идентификатор оценки;
    book_id — идентификатор книги;
    username — имя пользователя, оставившего оценку;
    rating — оценка книги.

**Таблица `reviews`** содержит данные о пользовательских обзорах на книги:

    review_id — идентификатор обзора;
    book_id — идентификатор книги;
    username — имя пользователя, написавшего обзор;
    text — текст обзора.
    
**Схема данных**

![2](https://github.com/a-dergilev/yandex_da/assets/124772360/93e4eb2c-cbe8-429e-920b-13b9f89fba54)


## Общие результаты

- после первого января 2000 года было выпущено 819 книг зафиксированных в базе данных;
- издательством, выпустившим больше всего книг толще 50 страниц является `Penguin Books`;
- книги `J.K. Rowling/Mary GrandPré` имеют самую высокую среднюю оценку - 4.29 среди книг, получивших более 50 оценок;
- пользователи поставившие более 50 оценок книгам, в среднем оставляют 24.3 отзывов;
- для дальнейшего равзития сервиса, рекомендуем ознакомиться с составленным списком книг, полученного при решении **задачи №2**. Для каждой книги было посчитано общее количество пользовательских обзоров и средний пользовательский рейтинг. Возможно, эти данные помогут выявить интересные предложения для пользователей сервиса.
