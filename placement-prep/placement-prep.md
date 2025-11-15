<p align="center">
  <h1>🔥 Top SQL Interview Questions & Answers (Best for Placements)</h1>
</p>

# 1️⃣ What is SQL?

Answer:
SQL (Structured Query Language) is used to store, manage, and retrieve data from relational databases. It supports CRUD operations.

# 2️⃣ What is a Primary Key?

Answer:
A primary key uniquely identifies each record in a table.
- Must be unique
- Cannot be NULL
- Only one per table

# 3️⃣ What is a Foreign Key?

Answer:
A foreign key creates a relationship between two tables by referencing the primary key of another table.

# 4️⃣ Difference between DELETE, TRUNCATE, and DROP

Answer:

| Command      | Removes       | Rollback | Speed   |
| ------------ | ------------- | -------- | ------- |
| **DELETE**   | Row-by-row    | Yes      | Slow    |
| **TRUNCATE** | Entire data   | No       | Fast    |
| **DROP**     | Deletes table | No       | Fastest |

# 5️⃣ What are Joins?

Answer:
Joins combine rows from two or more tables based on a related column.

Types:
- INNER JOIN
- LEFT JOIN
- RIGHT JOIN
- FULL JOIN
- SELF JOIN

# 6️⃣ Explain INNER JOIN with example

Answer:
Returns only matching rows from both tables.

```sql
SELECT *
FROM students s
INNER JOIN courses c
ON s.id = c.student_id;
```

# 7️⃣ What is Normalization?

Answer:
Normalization organizes data to reduce redundancy and improve data integrity.

Normal forms:
- 1NF → Atomic values
- 2NF → No partial dependency
- 3NF → No transitive dependency

# 8️⃣ What is denormalization?

Answer:
Opposite of normalization — increases redundancy for faster read performance.
Used in analytics and reporting systems.

# 9️⃣ What is a Unique Key?

Answer:
Ensures all values are unique
Unlike PK, it can contain one NULL

# 🔟 What is the difference between WHERE and HAVING?
| WHERE                          | HAVING              |
| ------------------------------ | ------------------- |
| Used before grouping           | Used after grouping |
| Cannot use aggregate functions | Can use aggregates  |
| Filters rows                   | Filters groups      |

# 1️⃣1️⃣ What is an Index?

Answer:
Index speeds up searching by creating a pointer reference to rows.
It works like a book index → fast lookup.

Types:
- Primary index
- Unique index
- Composite index

# 1️⃣2️⃣ What is the difference between clustered and non-clustered index?
| Clustered Index     | Non-Clustered Index   |
| ------------------- | --------------------- |
| Sorts physical data | Separate structure    |
| Only 1 per table    | Many allowed          |
| Faster for ranges   | Slower than clustered |

# 1️⃣3️⃣ What is a View?

Answer:
A view is a virtual table based on a SELECT query.
```sql
CREATE VIEW top_students AS
SELECT name, marks FROM students WHERE marks > 90;
```

# 1️⃣4️⃣ What is a Subquery?

Answer:
A query inside another query.

Example:
```sql
SELECT name 
FROM students 
WHERE marks > (SELECT AVG(marks) FROM students);
```
# 1️⃣5️⃣ What is BETWEEN, IN, and LIKE used for?

Answer:
- BETWEEN → Range
- IN → Multiple values
- LIKE → Pattern matching

# 1️⃣6️⃣ How to find the second highest salary?

3 Best Methods:

Method 1:
```sql
SELECT MAX(salary)
FROM employees
WHERE salary < (SELECT MAX(salary) FROM employees);
```

Method 2 (ORDER BY):
```sql
SELECT salary 
FROM employees
ORDER BY salary DESC
LIMIT 1 OFFSET 1;
```

Method 3 (DISTINCT):
```sql
SELECT DISTINCT salary 
FROM employees
ORDER BY salary DESC
LIMIT 1 OFFSET 1;
```

# 1️⃣7️⃣ How to count total rows in a table?
```sql
SELECT COUNT(*) FROM employees;
```
# 1️⃣8️⃣ What is the ACID property?

Answer:

| Property            | Meaning                |
| ------------------- | ---------------------- |
| **A – Atomicity**   | All or nothing         |
| **C – Consistency** | Valid state maintained |
| **I – Isolation**   | No interference        |
| **D – Durability**  | Permanent changes      |

# 1️⃣9️⃣ What is a Composite Key?

Answer:
A key made of multiple columns that together uniquely identify a row.

# 2️⃣0️⃣ What is an AUTO_INCREMENT?

Answer:
Automatically generates increasing numeric values.
```sql
id INT PRIMARY KEY AUTO_INCREMENT
```

# ⭐ BONUS: SQL Practical Coding Questions (Frequently Asked)

# Q21: Find employees with salary > average salary
```sql
SELECT name 
FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```

# Q22: Find duplicate emails
```sql
SELECT email, COUNT(*)
FROM users
GROUP BY email
HAVING COUNT(*) > 1;
```

# Q23: Display highest salary in each department
```sql
SELECT department, MAX(salary)
FROM employees
GROUP BY department;
```

# Q24: List all customers who never ordered
```sql
SELECT name
FROM customers c
LEFT JOIN orders o
ON c.id = o.customer_id
WHERE o.customer_id IS NULL;
```

# Q25: Count employees in each city
```sql
SELECT city, COUNT(*)
FROM employees
GROUP BY city;
```
