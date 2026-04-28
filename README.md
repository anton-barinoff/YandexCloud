# ДЗ 1 - Яндекс Cloud / PySpark

## Цель
Научиться собирать витрину данных на PySpark с использованием Spark DataFrame API,
оконных функций и сохранением в HDFS и S3.

## Задача
Собрать витрину `mart_city_top_products` - топ-2 товара по выручке в каждом городе.

## Датафреймы
Сгенерированы внутри ноутбука:
- **users** (user_id, city)
- **orders** (order_id, user_id, product_id, qty, price)
- **products** (product_id, product_name)

## Шаги решения
1. Вычисление производной метрики `revenue = qty * price`
2. Объединение таблиц через join
3. Агрегация заказов, кол-ва товаров и выручки по ключам (city, product_id, product_name)
4. Вычисление топ-2 товара по выручке в каждом городе через оконную функцию `row_number()`
5. Сохранение в HDFS и S3 в формате Parquet с режимом overwrite
6. Повторное чтение и вывод результата для проверки

## Результат
Витрина сохранена в:
- HDFS: `/tmp/sandbox_zeppelin/mart_city_top_products/`
- S3: `s3a://hadoop22/mart_city_top_products/`

## Технологии
- Yandex Cloud Data Proc
- Apache Zeppelin
- PySpark 3.3.2
- HDFS, S3 (Object Storage), Parquet

## Структура репозитория
```
YandexCloud/
	- `notebooks/`
		- `mart_city_top_products_2MRNWT6AE` - ноутбук Zeppelin
		- `mart_city_top_products.ipynb` - Python-ноутбук
	- `screenshots/` - директория со снимками экрана
	- `.gitignore`
	- `LICENSE` - MIT License	
	- `README.md`
```
