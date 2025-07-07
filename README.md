# SQL Data Analysis Practice – Northwind

## Dataset Used
Northwind sample database (W3Schools SQL Tryit Editor)

---

## Objectives
✅ Practice fundamental SQL concepts:
- SELECT
- WHERE
- GROUP BY
- ORDER BY
- JOIN

---

## Table of Contents
1. [SELECT](#select)
2. [WHERE](#where)
3. [GROUP BY](#group-by)
4. [ORDER BY](#order-by)
5. [JOIN](#join)
6. [Key Learnings](#key-learnings)
7. [Author](#author)

---

## SELECT

### ➡️ Definition
The `SELECT` statement is used to **retrieve data from one or more tables** in a database.

### 🔍 Example Query

```sql
SELECT * FROM Customers;
```

## WHERE
### ➡️ Definition
The `WHERE` clause is used to **filter records that fulfill a specified condition**.

### 🔍 Example Query

```sql
SELECT ContactName, City 
FROM Customers
WHERE Country = 'Germany';
```

#### ✅ Explanation 
This retrieves the ContactName and City columns only for customers in Germany.


## GROUP BY
### ➡️ Definition
The `GROUP BY` clause is used to **group rows sharing a property so aggregate functions** (like COUNT, SUM) can be applied to each group.

### 🔍 Example Query
```sql

SELECT Country, COUNT(CustomerID) AS TotalCustomers
FROM Customers
GROUP BY Country;
```

### ✅ Explanation
This counts the number of customers in each country and displays the country name with its respective count.


## ORDER BY
### ➡️ Definition
The `ORDER BY` clause is used to **sort the result set in ascending (ASC) or descending (DESC) order**.

### 🔍 Example Query
```sql

SELECT TOP 5 ProductName, Price
FROM Products
ORDER BY Price DESC;
```

### ✅ Explanation
This lists the top 5 most expensive products from the Products table in descending order of price.

### 💡 Note:
In SQL Server, use TOP instead of LIMIT (which is used in MySQL/SQLite).


## JOIN
➡️ Definition
A `JOIN` clause is used to **combine rows from two or more tables**, based on a related column between them.

### 🔍 Example Query

```sql
SELECT Orders.OrderID, Customers.ContactName
FROM Orders
INNER JOIN Customers
ON Orders.CustomerID = Customers.CustomerID;
```

### ✅ Explanation
This returns a combined table showing each OrderID with the ContactName of the customer who placed the order.
