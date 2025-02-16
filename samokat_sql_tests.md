## Задания по SQL (VK)

*Базы данных лежат в директории `/tests` под номером задания.*

#### Сложность: средняя

[#97](tests/97/97.md) `Тестовое задание Самокат` Посчитать количество работающих складов на текущую дату по каждому городу. Вывести только те города, у которых количество складов более 80.
```sql
SELECT city, COUNT(*) AS warehouse_count
FROM warehouses
WHERE (date_close IS NULL OR date_close > DATE('now')) 
AND date_open <= DATE('now')
GROUP BY city
HAVING warehouse_count > 80;
![img_18.png](img_18.png)