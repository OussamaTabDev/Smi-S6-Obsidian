# **Chapter 2: Querying Data with SELECT**

The `SELECT` statement is the most important SQL command—it retrieves data from database tables.

---

## **🔹 Basic SELECT Syntax**

The basic syntax is:

```sql
SELECT column1, column2 FROM table_name;
```

Example:

```sql
SELECT first_name, last_name FROM employees;
```

To retrieve all columns, use `*`:

```sql
SELECT * FROM employees;
```

---

## **🔹 Filtering Data with WHERE**

Use the `WHERE` clause to filter records.

```sql
SELECT * FROM employees WHERE department_id = 10;
```

Operators you can use:

|Operator|Meaning|
|---|---|
|`=`|Equal to|
|`!=` or `<>`|Not equal to|
|`>`|Greater than|
|`<`|Less than|
|`BETWEEN`|Range check|
|`LIKE`|Pattern matching|
|`IN`|Matches multiple values|

Example:

```sql
SELECT * FROM employees WHERE salary > 5000;
```

Using `LIKE` for pattern matching:

```sql
SELECT * FROM employees WHERE first_name LIKE 'J%';
```

---

## **🔹 Sorting Data with ORDER BY**

Use `ORDER BY` to sort results in ascending (`ASC`) or descending (`DESC`) order.

```sql
SELECT first_name, salary FROM employees ORDER BY salary DESC;
```

---

## **🔹 Removing Duplicates with DISTINCT**

Use `DISTINCT` to return unique values.

```sql
SELECT DISTINCT department_id FROM employees;
```

---

## **📝 Quiz – Chapter 2**

1️⃣ Write an SQL query to retrieve all columns from the `employees` table.

2️⃣ How would you retrieve only `first_name` and `last_name` from the `employees` table?

3️⃣ Write an SQL query to find employees who work in department `30`.

4️⃣ How would you retrieve employees who earn more than `6000` in salary?

5️⃣ Write an SQL query to find employees whose first name starts with "A".

---

Post your answers, and I'll check them before we move to **Chapter 3: SQL Functions and Expressions!** 🚀