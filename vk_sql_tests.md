## Задания по SQL (VK)

*Базы данных лежат в директории `/tests` под номером задания.*

#### Сложность: легко

[#99](tests/99/99.md) `Тестовое задание VK` Посчитай доход с женской аудитории
```sql
SELECT SUM(t.price) AS total_revenue
FROM transactions t
JOIN users u ON t.user_id = u.id
WHERE u.gender = 'female';
```


#### Сложность: средняя

[#101](tests/101/101.md) `Тестовое задание VK` Выведи для каждого пользователя первое наименование, которое он заказал (первое по времени транзакции).
```sql
SELECT t.user_id, t.item
FROM transactions t
WHERE t.transaction_ts = (
    SELECT MIN(t2.transaction_ts) 
    FROM transactions t2 
    WHERE t2.user_id = t.user_id
);
```