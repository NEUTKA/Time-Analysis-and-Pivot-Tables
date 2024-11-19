# Урок 5: Время и сводные таблицы

## Задание 1
Имеются следующие данные о транзакциях в период с 01.12.2010 по 12.09.2011:

- **InvoiceNo** — номер транзакции
- **StockCode** — код товара
- **Description** — описание товара
- **Quantity** — количество единиц товара, добавленных в заказ
- **InvoiceDate** — дата транзакции
- **UnitPrice** — цена за единицу товара
- **CustomerID** — id клиента
- **Country** — страна, где проживает клиент

В данной задаче ссылка для считывания данных лежит в переменной `path_to_file`.
- Импортируйте `pandas` и прочитайте данные с кодировкой `ISO-8859-1`.
- Запишите полученный датафрейм в переменную `retail`, а названия колонок сохраните в переменную `retail_columns`.

## Задание 2
- Проверьте, встречаются ли в данных повторяющиеся наблюдения, и укажите их количество.
- Если дубликаты есть, удалите их из `retail`.

## Задание 3
Данные содержат записи как об успешных транзакциях, так и об отменённых. Если пользователь отменил заказ, в начале номера транзакции (`InvoiceNo`) ставится "C" (canceled).

- Определите, сколько всего транзакций отменили пользователи.
- Считайте, что каждая строка - это отдельная транзакция.

## Задание 4
Отфильтруйте данные и оставьте в `retail` только те заказы, где `Quantity > 0`.

- Укажите число оставшихся строк.

## Задание 5
- Посчитайте число заказов для каждого пользователя (`CustomerID`) из Германии (`Germany`).
- Оставьте только тех, кто совершил более `N` транзакций (`InvoiceNo`), где `N` – это 80-й процентиль.
- Запишите полученные `id` пользователей в переменную `germany_top` (только `id`, без других данных).

Примечание: отфильтрованные данные находятся в `retail`. Для каждого заказа может быть более одной строки.

## Задание 6
Используя объект с `id` пользователей (`germany_top`), отфильтруйте наблюдения, оставив только записи по интересующим нас пользователям.

- Запишите результирующий датафрейм в `top_retail_germany`.

Примечание: датафрейм с данными — `retail`, нужные `id` пользователей — `germany_top`.

## Задание 7
Сгруппируйте `top_retail_germany` по коду товара (`StockCode`).

- Определите, какой из продуктов добавляли в корзину чаще всего, кроме товара с кодом "POST".

Примечание: одним заказом считается единоразовая покупка любого количества товара, т.е. без учета `Quantity`.

## Задание 8
Вернитесь к анализу полного набора данных `retail`.

- Создайте колонку `Revenue` с суммой покупки, используя `Quantity` и `UnitPrice`.

Примечание: отфильтрованные данные находятся в `retail`.

## Задание 9
Для каждой транзакции (`InvoiceNo`) посчитайте финальную сумму заказа.

- В качестве ответа укажите топ-5 транзакций (`InvoiceNo`) по сумме заказа (через запятую с пробелом и в порядке убывания `TotalRevenue`).

# Lesson 5: Time and Pivot Tables

## Task 1  
The following transaction data is available for the period from 01.12.2010 to 12.09.2011:

- **InvoiceNo** — transaction number  
- **StockCode** — product code  
- **Description** — product description  
- **Quantity** — the number of product units added to the order  
- **InvoiceDate** — transaction date  
- **UnitPrice** — unit price of the product  
- **CustomerID** — customer ID  
- **Country** — customer's country  

The dataset is located at the path stored in the `path_to_file` variable.  
- Import `pandas` and read the data using the `ISO-8859-1` encoding.  
- Save the resulting DataFrame to a variable named `retail`, and the column names to a variable named `retail_columns`.

## Task 2  
- Check if there are duplicate entries in the data and specify their count.  
- If duplicates are found, remove them from `retail`.

## Task 3  
The data includes records of both successful and canceled transactions. If a transaction is canceled, its number (`InvoiceNo`) starts with "C" (canceled).  

- Determine how many transactions were canceled by customers.  
- Assume that each row represents a single transaction.

## Task 4  
Filter the data in `retail` to keep only the orders where `Quantity > 0`.

- Specify the number of remaining rows.

## Task 5  
- Calculate the number of orders made by each customer (`CustomerID`) from Germany (`Germany`).  
- Keep only the customers who made more than `N` transactions (`InvoiceNo`), where `N` is the 80th percentile.  
- Save the resulting `id`s of these customers to a variable named `germany_top` (only `id`s, without other data).  

**Note:** The filtered data is in `retail`. Each order can have more than one row.

## Task 6  
Using the customer IDs stored in `germany_top`, filter the data to keep only the records related to the customers of interest.  

- Save the resulting DataFrame to `top_retail_germany`.  

**Note:** The data to filter is in `retail`, and the IDs of interest are in `germany_top`.

## Task 7  
Group `top_retail_germany` by product code (`StockCode`).  

- Determine which product was added to the cart most frequently, excluding the product with the code "POST".  

**Note:** A single purchase of any product quantity counts as one addition to the cart, i.e., ignore `Quantity`.

## Task 8  
Return to analyzing the full dataset `retail`.  

- Create a column named `Revenue` that contains the total purchase amount using `Quantity` and `UnitPrice`.

**Note:** The filtered data is in `retail`.

## Task 9  
For each transaction (`InvoiceNo`), calculate the final total order amount.  

- Provide the top 5 transactions (`InvoiceNo`) by total order amount (`TotalRevenue`) as a comma-separated list in descending order of `TotalRevenue`.
