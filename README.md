## Контекст и цель

Была цель провести поисковое исследование на данных о студентах и курсах образовательной платформы за два года: выделить ключевые метрики и оценить их, провести сегментирование клиентов, провести сравнение курсов, оценить эффективность форм контроля

## Стек

### Python

- pandas - для работы с датафреймами 
- numpy - для вычислений 
- requests - для выгрузки данных 
- urlencode - для выгрузки данных 
- seaborn - для визуализации 
- matplotlib.pyplot - для визуализации

## Этапы работы

1.  Сопровождающей документации не было, поэтому первичным было определение на основе данных, что считать курсом
2.  Исследование данных на пропуски, выбросы, ошибки записи
3.  Исследование распределений
4.  Формирование вопросов, на которые надо ответить для понимания ситуации
5.  Ответы на вопросы:

-   Количество пользоватей, которые закончили только один курс
-   Самый сложный и самый простой экзамен
-   Средний срок сдачи экзаменов
-   Самые популярные предметы. Самый большой отток
-   Курс с самой низкой завершаемостью и самым долгим сроком сдачи

6.  Разработка по-юзерных метрик для клиентов и сегментация по этим метрикам

## Результат

На основе анализа этих данных у меня вырисовывается следующая рекомендация:

Класс, который мог бы нам приносить больше всего дохода, самый малочисленный. Это класс тех, кто заранее записывается на наши курсы, но при это посредственно с ними справляется (но справялется), я думаю, что этот класс можно увеличить в объёме за счёт компульсивных покупателей, "прогрев" их в промежутке между записью на курс и его началом, удерживая их, когда спадёт раж покупки

Также я предлагаю использовать полностью наши формы контроля, позволить завершать курсы за счёт накопленных оценок (об этом подробнее сказано по ходу ответа на последний вопрос), это предотвратит ситуации, где мы упускаем курсы из виду, потому что там не было экзаменов (таких курсов большинство)

Также стоит обратить внимание на случай, когда у нас были отписавшиеся студенты, которые не записывались. Возможно там баг, который требует нашего внимания

