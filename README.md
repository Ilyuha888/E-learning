# Промежуточный проект (e-learning)


## Про формат

В качетсве формата этой работы мною был выбрано повествование через юпитерский ноутбук + текстовое резюме в виде этого маркдауна

Почему? Так как не будет устной защиты работы, то нужен формат максимально нагруженный информацией (ведь я не смогу дополнить по ходу защиты, тогда подошла бы преза, конечно)

В ноутбуке я подробно прокомментирую свои шаги, иллюстрируя, как я буду писать код на работе, чтобы с ним могли работать коллеги

В маркдауне будет резюме с основными выводами, на основании которых я бы готовил выступления для своих нетехнических коллег (для заказчиков)

## Про бизнес
Продакт-менеджер Василий попросил нас проанализировать завершенные уроки и ответить на следующие вопросы:

## Про данные

У нас есть 3 csvшные таблицы: assessments.csv; studentAssessment.csv; studentRegistration.csv

### assessments.csv

#### Описание
Этот файл содержит информацию об оценках в тесте. Обычно каждый предмет в семестре включает ряд тестов с оценками, за которыми следует заключительный экзаменационный тест (экзамен).

#### Переменные
`code_module` — идентификационный код предмета.

`code_presentation` — семестр (Идентификационный код).

`id_assessment` — тест (Идентификационный номер ассессмента).

`assessment_type` — тип теста. Существуют три типа оценивания: оценка преподавателя (TMA), компьютерная оценка (СМА), экзамен по курсу (Exam).

`date` — информация об окончательной дате сдачи теста. Рассчитывается как количество дней с момента начала семестра. Дата начала семестра имеет номер 0 (ноль).

`weight` — вес теста в % в оценке за курс. Обычно экзамены рассматриваются отдельно и имеют вес 100%; сумма всех остальных оценок составляет 100%.

### courses.csv 

#### Описание
Файл содержит список предметов по семестрам.

#### Переменные
`code_module` — предмет (идентификационный код).

`code_presentation` — семестр (идентификационный код).

`module_presentation_length` — продолжительность семестра в днях.

### studentAssessment.csv

#### Описание
Этот файл содержит список предметов по семестрам.

#### Переменные
`id_assessment` — тест (идентификационный номер).

`id_student` — идентификационный номер студента.

`date_submitted` — дата сдачи теста студентом, измеряемая как количество дней с начала семестра.

`is_banked` — факт перезачета теста с прошлого семестра (иногда курсы перезачитывают студентам, вернувшимся из академического отпуска).

`score` — оценка учащегося в этом тесте. Диапазон составляет от 0 до 100. Оценка ниже 40 неудачная/неуспешная сдача теста.

### studentRegistration.csv

#### Описание
Этот файл содержит информацию о времени, когда студент зарегистрировался для прохождения курса в семестре.

#### Переменные
`code_module` — предмет (идентификационный код).

`code_presentation` — семестр (идентификационный код)

`id_student` — идентификационный номер студента.

`date_registration` — дата регистрации студента. Это количество дней, измеренное от начала семестра (например, отрицательное значение -30 означает, что студент зарегистрировался на прохождение курса за 30 дней до его начала).

`date_unregistration` — дата отмены регистрации студента с предмета. У студентов, окончивших курс, это поле остается пустым.

## Задачи/вопросы — ответы

#### Вопрос:
0. Для решения задачи провести предварительное исследование данных и сформулируй, что должно считаться курсом. Обосновать свой выбор можно с помощью фактов сдачи экзаменов, распределения студентов и уникального идентификатора курса.
#### Ответ:


#### Вопрос:
1. Сколько студентов успешно сдали только один курс? (Успешная сдача — это зачёт по курсу на экзамене) (7 баллов).
#### Ответ:


#### Вопрос:
2. Выяви самый сложный и самый простой экзамен: найди курсы и экзамены в рамках курса, которые обладают самой низкой и самой высокой завершаемостью. (10 баллов)
**завершаемость** = кол-во успешных экзаменов / кол-во всех попыток сдать экзамен
#### Ответ:


#### Вопрос:
3. По каждому предмету определи средний срок сдачи экзаменов (под сдачей понимаем последнее успешное прохождение экзамена студентом). (7 баллов) 
#### Ответ:


#### Вопрос:
4. Выяви самые популярные предметы (ТОП-3) по количеству регистраций на них. А также предметы с самым большим оттоком (ТОП-3). (8 баллов)
#### Ответ:


#### Вопрос:
5. Используя pandas, в период с начала 2013 по конец 2014 выяви семестр с самой низкой завершаемостью курсов и самыми долгими средними сроками сдачи курсов.  (15 баллов) 
#### Ответ:


#### Вопрос:
6. Часто для качественного анализа аудитории используют подходы, основанные на сегментации. Используя python, построй адаптированные RFM-кластеры студентов, чтобы качественно оценить свою аудиторию. В адаптированной кластеризации можешь выбрать следующие метрики: R - среднее время сдачи одного экзамена, F - завершаемость курсов, M - среднее количество баллов, получаемое за экзамен. Подробно опиши, как ты создавал кластеры. Для каждого RFM-сегмента построй границы метрик recency, frequency и monetary для интерпретации этих кластеров. Описание подхода можно найти тут (https://guillaume-martin.github.io/rfm-segmentation-with-python.html). (23 балла)
#### Ответ:



## Общие выводы

