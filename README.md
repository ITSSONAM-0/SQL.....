
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

---

# Introduction
SQL is the standard language for managing relational databases.

---

# What is a Database?
A structured digital storage of data used for efficient access and management.

---

# Types of Databases
- **Relational (SQL)** — Data stored in tables  
- **Non-relational (NoSQL)** — Document, key-value, graph, column-based  

---

# What is SQL?
SQL (Structured Query Language) is used to perform CRUD and manage relational DBs.

---

# Database Structure

---

# SQL Data Types
- Integer Types  
- Floating Types  
- VARCHAR, CHAR, TEXT  
- DATE, TIME, DATETIME  
- BOOLEAN  

---

# Types of SQL Commands
- **DDL** – CREATE, ALTER, DROP  
- **DML** – INSERT, UPDATE, DELETE  
- **DQL** – SELECT  
- **DCL** – GRANT, REVOKE  
- **TCL** – COMMIT, ROLLBACK, SAVEPOINT  

---

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

