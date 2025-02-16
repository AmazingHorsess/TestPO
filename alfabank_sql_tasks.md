## Задания по SQL (Alfabank)

*Базы данных лежат в директории `/tests` под номером задания.*

#### Сложность: средняя

[#93](tests/93/93.md) `Тестовое задание Альфа банк` Какой средний возраст клиентов, купивших Smartwatch (использовать наименование товара product.name) в 2024 году?
SELECT AVG(c.age) AS avg_age
FROM customers c
JOIN purchases p ON c.customer_key = p.customer_key
JOIN products pr ON p.product_key = pr.product_key
WHERE pr.name = 'Smartwatch'
AND strftime('%Y', p.date) = '2024';
![img_16.png](img_16.png)

[#94](tests/94/94.md) `Тестовое задание Альфа банк` Вывести имена покупателей, каждый из которых приобрёл Laptop и Monitor (использовать наименование товара product.name) в марте 2024 года?
SELECT c.name
FROM customers c
JOIN purchases p1 ON c.customer_key = p1.customer_key
JOIN products pr1 ON p1.product_key = pr1.product_key
JOIN purchases p2 ON c.customer_key = p2.customer_key
JOIN products pr2 ON p2.product_key = pr2.product_key
WHERE pr1.name = 'Laptop' 
AND pr2.name = 'Monitor'
AND strftime('%Y', p1.date) = '2024'
AND strftime('%m', p1.date) = '03'
AND strftime('%Y', p2.date) = '2024'
AND strftime('%m', p2.date) = '03';
![img_17.png](img_17.png)
.