# SQL Fundamentals Lab

## Overview

This project documents my hands-on experience learning Structured Query Language (SQL), the standard language used to interact with relational databases. The exercises focus on database creation, data retrieval, filtering, sorting, aggregation, joins, and database management operations.

The goal of this project is to build a strong foundation in database management and querying techniques commonly used in cybersecurity, data analysis, web development, and enterprise environments.

---

# Topics Covered

## Introduction to SQL

SQL (Structured Query Language) is used to communicate with relational database management systems (RDBMS) such as:

* MySQL
* PostgreSQL
* Microsoft SQL Server
* Oracle Database
* SQLite

SQL enables users to:

* Store data
* Retrieve information
* Modify records
* Manage database structures
* Control access permissions

---

# Database Operations

## Creating Databases

```sql
CREATE DATABASE company_db;
```

## Selecting a Database

```sql
USE company_db;
```

## Deleting a Database

```sql
DROP DATABASE company_db;
```

---

# Table Management

## Creating Tables

```sql
CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    department VARCHAR(50),
    salary DECIMAL(10,2)
);
```

## Viewing Table Structure

```sql
DESCRIBE employees;
```

## Deleting Tables

```sql
DROP TABLE employees;
```

---

# Data Manipulation

## Inserting Records

```sql
INSERT INTO employees (
    employee_id,
    first_name,
    last_name,
    department,
    salary
)
VALUES (
    1,
    'John',
    'Doe',
    'IT',
    75000
);
```

## Updating Records

```sql
UPDATE employees
SET salary = 80000
WHERE employee_id = 1;
```

## Deleting Records

```sql
DELETE FROM employees
WHERE employee_id = 1;
```

---

# Retrieving Data

## Selecting All Records

```sql
SELECT * FROM employees;
```

## Selecting Specific Columns

```sql
SELECT first_name, last_name
FROM employees;
```

## Filtering Results

```sql
SELECT *
FROM employees
WHERE department = 'IT';
```

---

# Sorting Data

## Ascending Order

```sql
SELECT *
FROM employees
ORDER BY salary ASC;
```

## Descending Order

```sql
SELECT *
FROM employees
ORDER BY salary DESC;
```

---

# Limiting Results

```sql
SELECT *
FROM employees
LIMIT 5;
```

---

# Aggregate Functions

## Count Records

```sql
SELECT COUNT(*)
FROM employees;
```

## Average Salary

```sql
SELECT AVG(salary)
FROM employees;
```

## Maximum Salary

```sql
SELECT MAX(salary)
FROM employees;
```

## Minimum Salary

```sql
SELECT MIN(salary)
FROM employees;
```

## Salary Total

```sql
SELECT SUM(salary)
FROM employees;
```

---

# Grouping Data

## GROUP BY

```sql
SELECT department,
       COUNT(*) AS total_employees
FROM employees
GROUP BY department;
```

## HAVING

```sql
SELECT department,
       COUNT(*) AS total_employees
FROM employees
GROUP BY department
HAVING COUNT(*) > 5;
```

---

# SQL Joins

## INNER JOIN

Returns matching records from both tables.

```sql
SELECT employees.first_name,
       departments.department_name
FROM employees
INNER JOIN departments
ON employees.department_id = departments.department_id;
```

## LEFT JOIN

Returns all records from the left table.

```sql
SELECT *
FROM employees
LEFT JOIN departments
ON employees.department_id = departments.department_id;
```

## RIGHT JOIN

Returns all records from the right table.

```sql
SELECT *
FROM employees
RIGHT JOIN departments
ON employees.department_id = departments.department_id;
```

---

# Subqueries

```sql
SELECT first_name,
       salary
FROM employees
WHERE salary >
(
    SELECT AVG(salary)
    FROM employees
);
```

---

# SQL Constraints

## Primary Key

```sql
employee_id INT PRIMARY KEY
```

## Unique

```sql
email VARCHAR(100) UNIQUE
```

## Not Null

```sql
first_name VARCHAR(50) NOT NULL
```

## Foreign Key

```sql
FOREIGN KEY (department_id)
REFERENCES departments(department_id)
```

---

# Database Security Concepts

Topics explored include:

* User authentication
* Database permissions
* Principle of least privilege
* SQL injection awareness
* Input validation
* Secure query practices

Example of parameterized query concept:

```sql
SELECT *
FROM users
WHERE username = ?;
```

---

# Skills Demonstrated

* Database creation and management
* Table creation and modification
* CRUD operations
* Data filtering and sorting
* Aggregate functions
* Data grouping
* Relational database concepts
* SQL joins
* Subqueries
* Constraints and keys
* Database security fundamentals

---

# Technologies Used

* SQL
* MySQL
* MariaDB
* PostgreSQL
* SQLite
* Command Line Interface (CLI)

---

# Key Takeaways

SQL is a foundational skill for cybersecurity professionals, data analysts, developers, and system administrators. Understanding how to query, manage, and secure databases enables efficient data handling and provides valuable insight into how modern applications store and retrieve information.

This project demonstrates core SQL concepts that serve as the foundation for advanced topics such as database administration, data analytics, business intelligence, and web application security.

---

## Author

Created as part of database and cybersecurity training focused on developing practical SQL skills for real-world environments.
