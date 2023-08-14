# Статус проекта
  `Завершен`

# Базовый SQL

## Задание

Необходимо проанализировать данные о фондах и инвестициях и написать запросы к базе.

**Таблица `acquisition`** содержит информацию о покупках одних компаний другими.
        
    первичный ключ id — идентификатор или уникальный номер покупки;
    внешний ключ acquiring_company_id — ссылается на таблицу company — идентификатор компании-покупателя, то есть той, что покупает другую компанию;
    внешний ключ acquired_company_id — ссылается на таблицу company — идентификатор компании, которую покупают;
    term_code — способ оплаты сделки:
    cash — наличными;
    stock — акциями компании;
    cash_and_stock — смешанный тип оплаты: наличные и акции.
    price_amount — сумма покупки в долларах;
    acquired_at — дата совершения сделки;
    created_at — дата и время создания записи в таблице;
    updated_at — дата и время обновления записи в таблице.

**Таблица `company`** содержит информацию о компаниях-стартапах.
    
    первичный ключ id — идентификатор, или уникальный номер компании;
    name — название компании;
    category_code — категория деятельности компании, например:
    news — специализируется на работе с новостями;
    social — специализируется на социальной работе.
    status — статус компании:
    acquired — приобретена;
    operating — действует;
    ipo — вышла на IPO;
    closed — перестала существовать.
    founded_at — дата основания компании;
    closed_at — дата закрытия компании, которую указывают в том случае, если компании больше не существует;
    domain — домен сайта компании;
    twitter_username — название профиля компании в твиттере;
    country_code — код страны, например, USA для США, GBR для Великобритании;
    investment_rounds — число раундов, в которых компания участвовала как инвестор;
    funding_rounds — число раундов, в которых компания привлекала инвестиции;
    funding_total — сумма привлечённых инвестиций в долларах;
    milestones — количество важных этапов в истории компании;
    created_at — дата и время создания записи в таблице;
    updated_at — дата и время обновления записи в таблице.

**Таблица `education`** содержит информацию об уровне образования сотрудников компаний.
    
    первичный ключ id — уникальный номер записи с информацией об образовании;
    внешний ключ person_id — ссылается на таблицу people — идентификатор человека, информация о котором представлена в записи;
    degree_type — учебная степень, например:
    BA — Bachelor of Arts — бакалавр гуманитарных наук;
    MS — Master of Science — магистр естественных наук.
    instituition — учебное заведение, название университета;
    graduated_at — дата завершения обучения, выпуска;
    created_at — дата и время создания записи в таблице;
    updated_at — дата и время обновления записи в таблице.

**Таблица `fund`** содержит информацию о венчурных фондах. 

    первичный ключ id — уникальный номер венчурного фонда;
    name — название венчурного фонда;
    founded_at — дата основания фонда;
    domain — домен сайта фонда;
    twitter_username — профиль фонда в твиттере;
    country_code — код страны фонда;
    investment_rounds — число инвестиционных раундов, в которых фонд принимал участие;
    invested_companies — число компаний, в которые инвестировал фонд;
    milestones — количество важных этапов в истории фонда;
    created_at — дата и время создания записи в таблице;
    updated_at — дата и время обновления записи в таблице.

**Таблица `funding_round`** содержит информацию о раундах инвестиций. 

    первичный ключ id — уникальный номер инвестиционного раунда;
    внешний ключ company_id — ссылается на таблицу company — уникальный номер компании, участвовавшей в инвестиционном раунде;
    funded_at — дата проведения раунда;
    funding_round_type — тип инвестиционного раунда, например:
    venture — венчурный раунд;
    angel — ангельский раунд;
    series_a — раунд А.
    raised_amount — сумма инвестиций, которую привлекла компания в этом раунде в долларах;
    pre_money_valuation — предварительная, проведённая до инвестиций оценка стоимости компании в долларах;
    participants — количество участников инвестиционного раунда;
    is_first_round — является ли этот раунд первым для компании;
    is_last_round — является ли этот раунд последним для компании;
    created_at — дата и время создания записи в таблице;
    updated_at — дата и время обновления записи в таблице.

**Таблица `investment`** содержит информацию об инвестициях венчурных фондов в компании-стартапы.

    первичный ключ id — уникальный номер инвестиции;
    внешний ключ funding_round_id — ссылается на таблицу funding_round — уникальный номер раунда инвестиции;
    внешний ключ company_id — ссылается на таблицу company — уникальный номер компании-стартапа, в которую инвестируют;
    внешний ключ fund_id — ссылается на таблицу fund — уникальный номер фонда, инвестирующего в компанию-стартап;
    created_at — дата и время создания записи в таблице;
    updated_at — дата и время обновления записи в таблице.

**Таблица `people`** содержит информацию о сотрудниках компаний-стартапов.
     
    первичный ключ id — уникальный номер сотрудника;
    first_name — имя сотрудника;
    last_name — фамилия сотрудника;
    внешний ключ company_id — ссылается на таблицу company — уникальный номер компании-стартапа;
    twitter_username — профиль сотрудника в твиттере;
    created_at — дата и время создания записи в таблице;
    updated_at — дата и время обновления записи в таблице.
    
**Схема данных**

![BD](https://github.com/a-dergilev/yandex_da/assets/124772360/f19b90f8-8397-4b74-be60-7b0533e42f26)