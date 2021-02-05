## Проект "Желтое такси в Нью-Йорке от МФТИ и Яндекс"
Финальный проект  "Желтое такси в Нью-Йорке" специализации  ["Машинное обучение и анализ данных"](https://www.coursera.org/specializations/machine-learning-data-analysis)


Задача проекта — научиться предсказывать количество поездок в следующие 1-6 часов в 102-х самых популярных районах Нью-Йорка. 
Районы заданы квадратами из файла regions - содержит идентификаторы (id) районов и географичекие координаты их границ.

Данные о поездках: 
* Первоночальные данные о поездках такси берутся с официального сайта Нью-Йорского такси [nyc.gov](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page)


**Порядок выполенения проекта:**

**Неделя 1**

Знакомство с данными за май 2016. Очистка данных от ошибок и аномалий, агрегирование поездок по времени их начала и соответсвующего id региона. Выделение 102-х регионов, где среднее количество поездок на менее 5.


**Неделя 2**

Визуализация распределения количества поездок в час за май 2016 с помощью библиотек basemap и folium. Отбор наиболее важных районов по пороговому значению.


**Неделя 3**

Прогнозирование ряда из произвольно выбранного района (Empire State Building) с помощью модели ARIMA с учетом сезонности на основе регрессионных признаков Фурье.


**Неделя 4**

Стандартизация временных рядов. Выбор оптимального количества кластеров (в моём случае 3). Кластеризация по id отобраных на второй недели рядов. Построение моделей временных рядов для центров кластеров.


**Неделя 5**

Сведения задачи массового прогнозирования к регрессионым моделям. 

Используемый набор признаков:
* Идентификатор географической зоны
* Дата и время
* Количество поездок в периоды, предшествующие прогнозируемому (за несколько часов, дней, недель)
* Синусы, косинусы и тренды, которые были использованны внутри регрессионной компоненты ARIMA 
* Результаты предсказаний недели 4.

Выбор среди следующих регрессионных моделей:
* LinearRegression
* Ridge
* XGB (лучший результат)

**Неделя 6**

Добавление в модель дополнительных признаков.

Из первоночальных данных были добавлены:
* средняя длительность поездок
* среднее количество пассажиров
* среднее расстояние по счётчику
* доли поездок, совершаемых по тарифам каждого из типов
* доли способов оплаты поездок
* средняя стоимость поездок
* доли провайдеров данных


**Неделя 6- Catboost**

Проведен эксперимент: данные с недели 6 были проанализированы с помощью модели Catboost, в итоге был получен лучший результат с ошибкой 16.27.

**Неделя 7**

Визуализация результатов с помощью ipywidgets, widgets.SelectionSlider и т.д..
Создание интерактивных карт и графиков.


**РЕЗУЛЬТАТ :**

[Kaggle Leaderboard](https://www.kaggle.com/c/yellowtaxi/leaderboard): Score = 16.07.

![](https://github.com/avaits/Yandex-NY-taxi/blob/main/c6w7-1.jpg)

![](https://github.com/avaits/Yandex-NY-taxi/blob/main/c6w7-2.jpg) 

