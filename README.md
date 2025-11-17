
<p align="center">
  <img src="./images/banner.png" alt="SQL Banner" />
</p>

<p align="center">
  <h1>SQL COMPLETE NOTES</h1>
</p>

![SQL](https://img.shields.io/badge/SQL-Structured%20Query%20Language-blue)
![MySQL](https://img.shields.io/badge/MySQL-Database-orange)
![Markdown](https://img.shields.io/badge/Documentation-Markdown-lightgrey)
![Version](https://img.shields.io/badge/Version-1.1-green)

---

# 📑 Table of Contents
- [Introduction](#introduction)
- [What is a Database?](#what-is-a-database)
- [Types of Databases](#types-of-databases)
- [What is SQL?](#what-is-sql)
- [Database Structure](#database-structure)
- [SQL Data Types](#sql-data-types)
- [Types of SQL Commands](#types-of-sql-commands)
- [Database Queries](#database-queries)
- [Table Queries](#table-queries)
- [Constraints](#constraints)
- [Keys](#keys)
- [Select & WHERE Clause](#select--where-clause)
- [Operators](#operators)
- [Sorting & Limiting](#sorting--limiting)
- [Aggregate Functions](#aggregate-functions)
- [Group By & Having](#group-by--having)
- [Update & Delete](#update--delete)
- [Alter Table](#alter-table)
- [Joins](#joins)
- [Self Join](#self-join)
- [UNION](#union)
- [Subqueries](#subqueries)
- [Views](#views)



# Introduction
SQL is the standard language for managing relational databases.



# What is a Database?
A structured digital storage of data used for efficient access and management.



# Types of Databases
- **Relational (SQL)** — Data stored in tables  
- **Non-relational (NoSQL)** — Document, key-value, graph, column-based  



# What is SQL?
SQL (Structured Query Language) is used to perform CRUD and manage relational DBs.



# Database Structure



# SQL Data Types
- Integer Types  
- Floating Types  
- VARCHAR, CHAR, TEXT  
- DATE, TIME, DATETIME  
- BOOLEAN  



# Types of SQL Commands
- **DDL** – CREATE, ALTER, DROP  
- **DML** – INSERT, UPDATE, DELETE  
- **DQL** – SELECT  
- **DCL** – GRANT, REVOKE  
- **TCL** – COMMIT, ROLLBACK, SAVEPOINT  



# Database Queries
```sql
CREATE DATABASE db_name;
DROP DATABASE db_name;
SHOW DATABASES;
USE db_name;
```
# Create Table
```sql
CREATE TABLE students (
  id INT PRIMARY KEY,
  name VARCHAR(50),
  marks INT
);
```
# Insert
```sql
INSERT INTO students (name, marks) VALUES ("Sonam", 90);
```
# Select
```sql
SELECT * FROM students;
```
# Constraints
- NOT NULL
- UNIQUE
- PRIMARY KEY
- FOREIGN KEY
- DEFAULT
-  CHECK
# Keys
- Primary Key — Unique & Not Null
- Foreign Key — Links two tables
  
# Select & WHERE Clause
```sql
SELECT * FROM students WHERE marks > 80;
```
# Operators
- Comparison → = != < > <= >=
- Logical → AND OR NOT
- Range → BETWEEN
- List → IN
- Pattern → LIKE

# Sorting & Limiting
```sql
SELECT * FROM students ORDER BY marks DESC;
SELECT * FROM students LIMIT 5;
```

# Aggregate Functions
```sql
SELECT COUNT(*), MAX(marks), AVG(marks) FROM students;
```
# Group By & Having
```sql
SELECT city, COUNT(*) 
FROM students 
GROUP BY city 
HAVING COUNT(*) > 5;
```
# Update & Delete
```sql
UPDATE students SET marks = 95 WHERE id = 1;
DELETE FROM students WHERE marks < 40;
```
# Alter Table
```sql
ALTER TABLE students ADD COLUMN age INT;
ALTER TABLE students DROP COLUMN age;
```

# Joins
## Inner Join
```sql
SELECT * 
FROM students s 
INNER JOIN courses c 
ON s.id = c.student_id;
```

# Left Join
```sql
SELECT *
FROM students s
LEFT JOIN courses c
ON s.id = c.student_id;
```
# Self Join
```sql
SELECT a.name, b.name AS manager
FROM employees a
JOIN employees b
ON a.manager_id = b.id;
```

# UNION
```sql
SELECT name FROM table1
UNION
SELECT name FROM table2;
```

# Subqueries
```sql
SELECT name
FROM students
WHERE marks > (SELECT AVG(marks) FROM students);
```

# Views
```sql
CREATE VIEW toppers AS
SELECT name, marks FROM students WHERE marks > 90;
```

# Good luck....

