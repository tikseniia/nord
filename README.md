# Крайний Север: районные коэффициенты и процентная надбавка

Смотреть: https://tikseniia.github.io/northern-benefits/

Проект рассказывает о зарплатных льготах в районах Крайнего Севера: районный коэффициент и процентная надбавка за стаж работы. На интерактивной карте показано, какие районы субъектов РФ относятся к Крайнему Северу, сколько людей там проживает постоянно, какой минимальный районный коэффициент там установлен. С помощью калькулятора зарплаты можно посчитать, как увеличивается оклад человека, если бы он работал на Севере.

Сделано для проекта "Неравенства" - https://github.com/infoculture/datatasks/issues/23

## Описание данных

Список районов Крайнего Севера и данные о коэффициентах и надбавках собраны из нормативных актов на сайте Консультанта. Эти данные находятся в массиве в файле *data/benefits.js*. Файл разделен на два массива: для достигших 30 летнего возраста и молодых работников, проживающих в районе Крайнего Севера больше года. Структура массивов:
  * **name** - название района
  * **start_date** - количество полугодий, с которых начисляется надбавка
  * **end** - максимальный размер процентной надбавки
  * **step** - %, на который увеличивается надбавка каждое полугодие
  * **coef** - минимальный районный коэффициент для этого района
  * **law** - акт, устанавливающий процентную надбавку
  
Данные о населении взяты с сайта ГосСтата - http://www.gks.ru/wps/wcm/connect/rosstat_main/rosstat/ru/statistics/publications/catalog/afc8ea004d56a39ab251f2bafc3a6fce. Структура массива в файле *data/nord.js*:
  * **name** - название субъекта РФ
  * **population** - суммарное население районов Крайнего Севера данного субъекта
  * **subjects** - список районов Крайнего Севера
  * **subjects.name** - название района
  * **subjects.law** - акт, утанавливающий статус района Крайнего Севера
  * **subjects.population** - население района
  * **subjects.population.year** - год показателя
  * **subjects.population.count** - количество населения за данный год

## Источники
  * **Список районов Крайнего Севера** - http://www.consultant.ru/document/cons_doc_LAW_403/e0ea98970eab53abef3339d0a701bed7dd8420a1/#dst100010
  * **Районные коэффициенты и надбавки** - http://www.consultant.ru/document/cons_doc_LAW_118861/
  * **Координаты субъектов РФ** - https://github.com/alt-dmitry/RussianMap
  * Карта создана с помощью Mapbox - https://www.mapbox.com/

## Допущения
  * Проект не учитывает районы, приравненные к районам Крайнего Севера
  * Карта показывает субъекты РФ, а не конкретные районы Крайнего Севера
  * Рассчет происходит без учета конкретного района субъекта и профессии пользователя
