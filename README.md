# Data Mining: предобработка данных

Практическая работа по предобработке данных на датасете [Hotel Booking Demand](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand) (Kaggle, 119 тыс. бронирований). Алгоритмы написаны вручную, а библиотеки (numpy, scipy) нужны только для проверки результатов.

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?logo=pandas&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?logo=jupyter&logoColor=white)

## Содержание

**0. Очистка данных:** удаление колонок, через которые утекает целевая переменная (`reservation_status`, `assigned_room_type`), пропуски, некорректные записи и выбросы.

**1. Агрегация**
- Многоуровневая агрегация `market_segment × customer_type` (mean, median, IQR) с отметкой групп, где n < 30
- Взвешенное среднее ADR по длительности проживания и разбор, почему оно расходится с обычным средним
- Потеря вариативности при агрегации (коэффициент вариации на разных уровнях детализации)

**2. Сэмплирование**
- Reservoir sampling с нуля и статистическая проверка равномерности выборки
- Сравнение простой случайной, стратифицированной и convenience-выборки через KL-дивергенцию и χ²
- Bootstrap-доверительные интервалы и эмпирический размер выборки (закон 1/√n)

**3. Отбор признаков:** итеративное удаление мультиколлинеарных признаков по VIF и другие методы.

**4. Создание признаков**

После каждого шага текстом записаны выводы с конкретными числами.

Ноутбук: [`Practice1_Hotel_Bookings.ipynb`](Practice1_Hotel_Bookings.ipynb)

## Запуск
Скачайте `hotel_bookings.csv` с Kaggle и положите рядом с ноутбуком:
```bash
pip install numpy pandas matplotlib scipy scikit-learn statsmodels jupyter
jupyter notebook Practice1_Hotel_Bookings.ipynb
```
