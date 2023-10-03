# SQL Join
A SQL join is a database operation that combines rows from two or more tables based on a related column between them. The purpose of a join is to retrieve data from multiple tables and present it as a single result set, allowing you to analyze and query data from different parts of a database together. SQL joins are fundamental for working with relational databases and performing complex queries.



## INNER JOIN
Retrieves rows from both tables that have matching values in the specified columns.
Excludes rows from both tables that do not have a match.
This is the most common type of join.
```
SELECT employees.name, departments.department_name
FROM employees
INNER JOIN departments ON employees.department_id = departments.department_id;
```

## LEFT JOIN (or LEFT OUTER JOIN)
Retrieves all rows from the left table and the matched rows from the right table.
If there is no match in the right table, it returns NULL values for columns from the right table.
```
SELECT customers.customer_name, orders.order_date
FROM customers
LEFT JOIN orders ON customers.customer_id = orders.customer_id;
```

## RIGHT JOIN (or RIGHT OUTER JOIN)
Retrieves all rows from the right table and the matched rows from the left table.
If there is no match in the left table, it returns NULL values for columns from the left table.
```
SELECT orders.order_date, customers.customer_name
FROM orders
RIGHT JOIN customers ON orders.customer_id = customers.customer_id;
```

## FULL OUTER JOIN
Retrieves all rows from both tables and returns NULL values for columns where there are no matches.

```
SELECT employees.name, projects.project_name
FROM employees
FULL OUTER JOIN projects ON employees.employee_id = projects.employee_id;
```

## SELF JOIN
A self join is used to join a table with itself. This is often used when a table has a hierarchical structure or when you want to compare rows within the same table.
```
SELECT e1.name AS employee, e2.name AS manager
FROM employees AS e1
LEFT JOIN employees AS e2 ON e1.manager_id = e2.employee_id;
```
