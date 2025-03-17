# **Chapter 1: Introduction to SQL*Plus and Basic Commands**

## **📌 Overview of SQL*Plus**

SQL*Plus is a command-line tool for interacting with Oracle databases. It allows you to:  
✔️ Run SQL queries and PL/SQL code  
✔️ Manage database objects (tables, views, indexes, etc.)  
✔️ Automate tasks with scripts

---

## **🔹 Connecting to an Oracle Database**

To start SQL*Plus, open a terminal or command prompt and type:

```sh
sqlplus /nolog
```
Output:
```
C:\Users\OussamaTab>sqlplus /nolog

SQL*Plus: Release 21.0.0.0.0 - Production on Tue Mar 11 11:48:10 2025
Version 21.3.0.0.0

Copyright (c) 1982, 2021, Oracle.  All rights reserved.
```

Then, connect using:

```sh
CONNECT username/password@localhost:1521/orcl
```

Or

```
Enter user-name: sqlplus
Enter password: as sysdba
```

or for a remote database:

```sh
CONNECT username/password@host:port/service_name
```

To check your connection, run:

```sql
SELECT SYSDATE FROM dual;
```

```
SYSDATE
---------
11-MAR-25
```

---

## **🔹 Basic SQL*Plus Commands**

| Command                    | Description                       | Output          |
| -------------------------- | --------------------------------- | --------------- |
| `SHOW USER;`               | Displays the current user         | `USER is "SYS"` |
| `DESCRIBE table_name;`     | Shows table structure             | ``              |
| `EXIT;`                    | Closes SQL*Plus                   | ``              |
| `CLEAR SCREEN;`            | Clears the screen                 | ``              |
| `SELECT * FROM employees;` | Retrieves all rows from the table | ``              |

---

## **🔹 Running SQL Queries**

Example:

```sql
SELECT first_name, last_name FROM employees;
```

Filters:

```sql
SELECT * FROM employees WHERE department_id = 10;
```

Sorting:

```sql
SELECT * FROM employees ORDER BY salary DESC;
```

---

## **🔹 Running SQL Scripts in SQL*Plus**

If you have an SQL script (`my_script.sql`), run it with:

```sh
@my_script.sql
```

---

## **📝 Quiz – Chapter 1**

1️⃣ What is SQL_Plus used for?  
2️⃣ How do you connect to an Oracle database in SQL_Plus?  
3️⃣ What command shows the structure of a table?  
4️⃣ How do you clear the screen in SQL*Plus?  
5️⃣ What command retrieves all records from the `employees` table?

---
Answers :
1️⃣ What is SQL_Plus used for?  
	Sql_Plus is command line used for managing tables or databases 
	It can run sql query and Pl/sql code  
2️⃣ How do you connect to an Oracle database in SQL_Plus?  
   1. first method : 
		print in cmd `sqlplus /nolog`
   2. Sec method:
	   1.  open `SqlPlus`
	   2. Insert username and password
3️⃣ What command shows the structure of a table?  
	`DESCRIBE table_name`
4️⃣ How do you clear the screen in SQL*Plus?  
	 `Clear Screen`
	 
5️⃣ What command retrieves all records from the `employees` table?
	`SELECT * FROM employees`

---

When you're ready, answer the quiz, and I'll check your answers before moving to **Chapter 2: Querying Data with SELECT**! 🚀