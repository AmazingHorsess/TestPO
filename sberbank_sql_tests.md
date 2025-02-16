## Задания по SQL (Sberbank)

*Базы данных лежат в директории `/tests` под номером задания.*

#### Сложность: легко

[#103](tests/103/103.md) `Тестовое задание Сбербанк` Вывести список имён сотрудников, получающих большую заработную плату, чем у непосредственного руководителя.
```sql
SELECT e.name
FROM employees e
JOIN employees chief ON e.chief_id = chief.id
WHERE e.salary > chief.salary;
```
![img_19.png](img_19.png)
