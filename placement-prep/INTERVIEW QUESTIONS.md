<p align="center">
  <h1>🔥TOP-TIER SQL INTERVIEW QUESTIONS</h1>
</p>

# 1️⃣ Difference between WHERE and HAVING with real example

Where filters rows
Having filters groups

Example:

```sql
SELECT department, COUNT(*)
FROM employees
WHERE salary > 50000
GROUP BY department
HAVING COUNT(*) > 10;
```

# 2️⃣ What is the difference between UNION and UNION ALL? Which one is faster?
| UNION               | UNION ALL        |
| ------------------- | ---------------- |
| Removes duplicates  | Keeps duplicates |
| Slow (sorting cost) | Fast             |


👉 UNION ALL is faster because no distinct operation.

# 3️⃣ What is a CTE? How is it different from Subquery?
 CTE = Common Table Expression
 
 Readable, reusable, temporary result set.

Example:
```sql
WITH high_salary AS (
    SELECT * FROM employees WHERE salary > 50000
)
SELECT name FROM high_salary;
```


- ✔ Easier to maintain
- ✔ Better for recursive queries
- ✔ Improves readability

# 4️⃣ What is a window function? Give example.

Window function performs operations across a set of rows related to the current row.

Example:
```sql
SELECT 
   name, salary,
   RANK() OVER (ORDER BY salary DESC) AS rank
FROM employees;
```


Used for:
- Ranking
- Running totals
- Moving averages

# 5️⃣ Difference between RANK(), DENSE_RANK(), and ROW_NUMBER()
| Function         | Output  | Duplicate Handling |
| ---------------- | ------- | ------------------ |
| **ROW_NUMBER()** | 1,2,3,4 | No duplicates      |
| **RANK()**       | 1,2,2,4 | Skips numbers      |
| **DENSE_RANK()** | 1,2,2,3 | No skipping        |

# 6️⃣ Find the 3rd highest salary without LIMIT
```sql
SELECT salary 
FROM employees e1
WHERE 3 = (
  SELECT COUNT(DISTINCT salary)
  FROM employees e2
  WHERE e2.salary > e1.salary
);
```

# 7️⃣ What are transactions? Explain ACID in detail with example

Transaction = A group of operations executed together

Example:

```sql
START TRANSACTION;
UPDATE accounts SET balance = balance - 500 WHERE id = 1;
UPDATE accounts SET balance = balance + 500 WHERE id = 2;
COMMIT;
```

# 8️⃣ What is deadlock? When does it occur?

Two transactions waiting on each other causing a permanent lock.

Occurs when:
- Both transactions hold a lock
- Both require each other's lock

👉 Solved using timeout, lock hierarchy.

# 9️⃣ Explain indexes in detail. How do they work internally?

Indexes use B-Tree or Hash table structure.

Advantages:
- Faster SELECT
- Faster search
Disadvantages:
- Slower INSERT/UPDATE
- Takes memory

# 🔟 Why is COUNT(1) faster than COUNT(*)?

Myth: COUNT(1) is faster
Truth: Both are SAME in modern DBMS.
Database optimizer converts both to the same execution plan.

# 🔥 More Advanced & Practical SQL Questions (Real Company Rounds)
## 11️⃣ Find the department with the highest average salary
```sql
SELECT department
FROM employees
GROUP BY department
ORDER BY AVG(salary) DESC
LIMIT 1;
```

# 12️⃣ Show employee with highest salary in each department
```sql
SELECT department, name, salary
FROM employees e
WHERE salary = (
    SELECT MAX(salary)
    FROM employees
    WHERE department = e.department
);
```

# 13️⃣ Show customers who ordered at least 5 times
```sql
SELECT customer_id
FROM orders
GROUP BY customer_id
HAVING COUNT(*) >= 5;
```

# 14️⃣ Show employees who have the same salary
```sql
SELECT salary, COUNT(*)
FROM employees
GROUP BY salary
HAVING COUNT(*) > 1;
```

# 15️⃣ What is Referential Integrity?

Ensures foreign key values must exist in the parent table.
Prevents:
- Orphan records
- Inconsistent data

# 🧠 Deep Concept Questions (Most Candidates Fail These)
# 16️⃣ Why do we use surrogate keys instead of natural keys?

Surrogate key = artificial (AUTO_INCREMENT)
Natural key = real-world value (email, phone)

Surrogate keys:
- ✔ Faster
- ✔ Smaller
- ✔ Avoid updates
- ✔ No business dependency

# 17️⃣ Difference between DELETE with and without WHERE
```sql
DELETE FROM table;       -- DELETE ALL rows
DELETE FROM table WHERE; -- DELETE specific rows
```

# 18️⃣ Why do we avoid SELECT * in production?
- Slow
- Memory waste
- Loads unnecessary columns
- Breaks if new columns added

# 19️⃣ Explain the concept of Cardinality in SQL
 Cardinality = uniqueness of values.
 
- High cardinality → many unique values (email, phone)
- Low cardinality → few unique values (gender, boolean)

#  20️⃣ What is a Composite Index?

Index on multiple columns.

Example:
```sql

CREATE INDEX idx_user_city ON users (city, age);
```



CREATE INDEX idx_user_city ON users (city, age);
