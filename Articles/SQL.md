---
Autor: Vinícius Bohrer dos Santos
Curso: Sololearn
---

# SQL

## Introduction

A **database** is a collection of data that is organized in a manner that facilitates ease of access, as well as efficient management and updating.
A database is made up of **tables** that store relevant information.

### Tables

A table stores and displays data in a structured format consisting of **columns** and **rows** that are similar to those seen in Excel spreadsheets.

> A table has a specified number of columns but can have any number of rows.

### Primary Key

A primary key is a field in the table that uniquely identifies the table records.
The primary key's main features:

- It must contain a **unique value** for each row.
- It cannot contain **NULL** values.

### What is SQL?

**SQL** stands for **S**tructured **Q**uery **L**anguage. SQL can:

- insert, update, or delete records in a database.
- create new databases, table, stored procedures, views.
- retrieve data from a database, etc.

SQL is an ANSI (American National Standards Institute) standard, but there are different versions of the SQL language.
Most SQL database programs have their own proprietary extensions in addition to the SQL standard, but all of them support the major commands.

## Basic Concepts

The SQL `SHOW` statement displays information contained in the database and its tables. This helpful tool lets you keep track of your database contents and remind yourself about the structure of your tables.
The `SHOW DATABASES` command lists the databases managed by the server.
The `SHOW TABLES` command is used to display all of the tables in the currently selected MySQL database.
`SHOW COLUMNS` displays information about the columns in a given table.
The `SELECT` statement is used to select data from a database.

### Syntax Rules

- Remember to end each SQL statement with a **semicolon** to indicate that the statement is complete and ready to be interpreted.
- SQL is case **insensitive**.
- It is common practice to write all SQL commands in **upper-case**.
- A single SQL statement can be placed on one or more text lines. In addition, multiple SQL statements can be combined on a single text line.
- White spaces and multiple lines are ignored in SQL.
- Combined with proper spacing and indenting, breaking up the commands into logical lines will make your SQL statements much easier to read and maintain.
- In SQL, the asterisk means **all**.

### DISCTINCT & LIMIT

In situations in which you have multiple duplicate records in a table, it might make more sense to return only unique records, instead of fetching the duplicates.
The SQL `DISTINCT` keyword is used in conjunction with SELECT to eliminate all duplicate records and return only unique ones.

```sql
SELECT DISTINCT column_name1, column_name2 FROM table_name;
```

> The DISTINCT keyword only fetches the unique values.

By default, all results that satisfy the conditions specified in the SQL statement are returned. However, sometimes we need to retrieve just a subset of records. In MySQL, this is accomplished by using the `LIMIT` keyword.

```sql
SELECT column list FROM table_name LIMIT [number of records];
```

You can also pick up a set of records from a particular **offset**.
In the following example, we pick up **four** records, starting from the **third** position:

```sql
SELECT ID, FirstName, LastName, City FROM customers LIMIT 3, 4;
```

> The reason that it produces results starting from ID number four, and not three, is that MySQL starts counting from **zero**, meaning that the offset of the first row is 0, not 1.

### Sorting Results

`ORDER BY` can sort retrieved data by multiple columns. When using `ORDER BY` with more than one column, separate the list of columns to follow `ORDER BY` with **commas**.

To order by **LastName** and **Age**:

```sql
SELECT * FROM customers ORDER BY LastName, Age;
```

## Filtering, Functions, Subqueries

### The WHERE Statement

The **WHERE** clause is used to extract only those records that fulfill a specified criterion.

```sql
SELECT column_list FROM table_name WHERE condition;
```

### SQL Operators

**Comparison Operators** and **Logical Operators** are used in the WHERE clause to filter the data to be selected.
The following comparison operators can be used in the WHERE clause:

![img](https://api.sololearn.com/DownloadFile?id=2805)

```sql
SELECT * FROM customers WHERE ID != 5;
```

### The BETWEEN Operator

The BETWEEN operator selects values within a range. The first value must be lower bound and the second value, the upper bound.

```sql
SELECT * FROM customers WHERE ID BETWEEN 3 AND 7;
```

> 3 and 7 were included

```sql
SELECT ID, FirstName, LastName, City FROM customers WHERE City = 'New York';
```

> If your text contains an apostrophe (single quote), you should use two single quote characters to escape the apostrophe. For example: 'Can''t'.

### Logical Operators

```sql
SELECT ID, FirstName, LastName, Age FROM customers WHERE Age >= 30 AND Age <= 40;
```

```sql
SELECT * FROM customers WHERE City = 'New York' OR City = 'Chicago';
```

```sql
SELECT * FROM customers WHERE City = 'New York' AND (Age=30 OR Age=35);
```

### The IN Operator

The **IN** operator is used when you want to compare a column with more than one value.

```sql
SELECT * FROM customers WHERE City = 'New York' OR City = 'Los Angeles' OR City = 'Chicago';
```

Is equal to:

```Sql
SELECT * FROM customers WHERE City IN ('New York', 'Los Angeles', 'Chicago');
```

### The NOT IN Operator

```sql
SELECT * FROM customers WHERE City NOT IN ('New York', 'Los Angeles', 'Chicago');
```

> The NOT IN operator allows you to exclude a list of specific values from the result set.

### The CONCAT Function

The **CONCAT** function is used to concatenate two or more text values and returns the concatenating string.
Let's concatenate the *FirstName* with the *City*, separating them with a *comma*:

```sql
SELECT CONCAT(FirstName, ', ' , City) FROM customers;
```

### The AS Keyword

A concatenation results in a new column. The default column name will be the CONCAT function.
You can assign a custom name to the resulting column using the **AS** keyword:

```sql
SELECT CONCAT(FirstName,', ', City) AS new_column FROM customers;
```

### Arithmetic Operators

Arithmetic operators perform arithmetical operations on numeric operands. The Arithmetic operators include addition (+), subtraction (-), multiplication (*) and division (/).

```sql
SELECT ID, FirstName, LastName, Salary+500 AS Salary FROM employees;
```

### The UPPER Function

The **UPPER** function converts all letters in the specified string to uppercase.
The **LOWER** function converts the string to lowercase.

```Sql
SELECT FirstName, UPPER(LastName) AS LastName FROM employees;
```

### SQRT and AVG

```sql
SELECT Salary, SQRT(Salary) FROM employees;
```

```sql
SELECT AVG(Salary) FROM employees;
```

> Another way to do the SQRT is to use POWER with the 1/2 exponent. However, SQRT seems to work faster than POWER in this case.

### The SUM Function

```sql
SELECT SUM(Salary) FROM employees;
```

### Subqueries

A **subquery** is a query within another query.
Let's consider an example. We might need the list of all employees whose salaries are greater than the average.
First, calculate the average:

```sql
SELECT AVG(Salary) FROM employees;
```

As we already know the average, we can use a simple WHERE to list the salaries that are **greater** than that number.

```sql
SELECT FirstName, Salary FROM employees WHERE Salary > 3100 ORDER BY Salary DESC;
```

>The **DESC** keyword sorts results in **descending** order.
>Similarly, **ASC** sorts the results in **ascending** order.

A single subquery will return the same result more easily.

```sql
SELECT FirstName, Salary FROM employees
WHERE Salary > (SELECT AVG(Salary) FROM employees)
ORDER BY Salary DESC;
```

### The Like Operator

The **LIKE** keyword is useful when specifying a **search condition** within your WHERE clause.

```sql
SELECT column_name(s) FROM table_name WHERE column_name LIKE pattern;
```

SQL **pattern** matching enables you to use "_" to match any single character and "%" to match an arbitrary number of characters (including zero characters).
For example, to select employees whose *FirstNames* begin with the letter **A**, you would use the following query:

```sql
SELECT * FROM employees WHERE FirstName LIKE 'A%';
```

### The MIN Function

The **MIN** function is used to return the minimum value of an expression in a SELECT statement.
For example, you might wish to know the minimum salary among the employees.

```sql
SELECT MIN(Salary) AS Salary FROM employees;
```

## JOIN, Table Operations

All of the queries shown up until now have selected from just one table at a time.
One of the most beneficial features of SQL is the ability to combine data from two or more tables.

> In SQL, "**joining tables**" means combining data from two or more tables. A table join creates a **temporary table** showing the data from the joined tables.

To join the two tables, specify them as a comma-separated list in the FROM clause:

```mysql
SELECT customers.ID, customers.Name, orders.Name, orders.Amount
FROM customers, orders
WHERE customers.ID=orders.Customer_ID
ORDER BY customers.ID;
```

### Types of Join

```mysql
SELECT ct.ID, ct.Name, ord.Name, ord.Amount
FROM customers AS ct, orders AS ord
WHERE ct.ID=ord.Customer_ID
ORDER BY ct.ID;
```

The following are the types of JOIN that can be used in MySQL:

- **INNER JOIN**: Is equivalent to JOIN. It returns rows when there is a match between the tables.

  ```mysql
  SELECT column_name(s)
  FROM table1 INNER JOIN table2 
  ON table1.column_name=table2.column_name;
  ```

  ![img](https://api.sololearn.com/DownloadFile?id=2833)

- **LEFT JOIN**: Returns all rows from the left table, even if there are no matches in the right table.

  ```mysql
  SELECT table1.column1, table2.column2...
  FROM table1 LEFT OUTER JOIN table2
  ON table1.column_name = table2.column_name;
  ```

  ![img](https://api.sololearn.com/DownloadFile?id=2834)

- **RIGHT JOIN**: Returns all rows from the right table, even if there are no matches in the left table.

  ```mysql
  SELECT table1.column1, table2.column2...
  FROM table1 RIGHT OUTER JOIN table2
  ON table1.column_name = table2.column_name;
  ```

  ![img](https://api.sololearn.com/DownloadFile?id=2838)

> There are other types of joins in the SQL language, but they are not supported by MySQL.

### UNION

Occasionally, you might need to combine data from multiple tables into one comprehensive dataset. This may be for tables with similar data within the same database or maybe there is a need to combine similar data across databases or even across servers.

To accomplish this, use the **UNION** and **UNION ALL** operators.

**UNION** combines multiple datasets into a single dataset, and removes any existing duplicates.
**UNION ALL** combines multiple datasets into one dataset, but does not remove duplicate rows.

> UNION ALL is faster than UNION, as it does not perform the duplicate removal operation over the data set.

The **UNION** operator is used to combine the result-sets of two or more SELECT statements.

All SELECT statements within the UNION must have the **same number of columns**. The columns must also have the same **data types**. Also, the columns in each SELECT statement must be in the same order.

```mysql
SELECT ID, FirstName, LastName, City FROM First
UNION
SELECT ID, FirstName, LastName, City FROM Second;
```

#### TIP

If your columns don't match exactly across all queries, you can use a **NULL (or any other)** value such as:

```mysql
SELECT FirstName, LastName, Company FROM businessContacts
UNION
SELECT FirstName, LastName, NULL FROM otherContacts;
```

The following SQL statement uses UNION ALL to select data from the **First** and **Second** tables:

```mysql
SELECT ID, FirstName, LastName, City FROM First
UNION ALL
SELECT ID, FirstName, LastName, City FROM Second;
```

>  The result set includes the duplicate rows as well.

### The INSERT Statement

SQL tables store data in rows, one row after another. The **INSERT INTO** statement is used to add **new rows** of data to a table in the database.

The SQL INSERT INTO syntax is as follows:

```mysql
INSERT INTO table_name
VALUES (value1, value2, value3,...);
```

> Make sure the order of the values is in the same order as the columns in the table.

> When inserting records into a table using the SQL INSERT statement, you must provide a value for every column that does not have a default value, or does not support NULL.

Alternatively, you can specify the table's column names in the INSERT INTO statement:

```mysql
INSERT INTO Employees (ID, FirstName, LastName, Age) 
VALUES (8, 'Anthony', 'Young', 35);
```

> You can specify your own column order, as long as the values are specified in the same order as the columns.

It is also possible to insert data into **specific** columns only.

```mysql
INSERT INTO Employees (ID, FirstName, LastName)
VALUES (9, 'Samuel', 'Clark'); #forgeting age
```

> The *Age* column for that row automatically became **0**, as that is its default value.

### The UPDATE Statement

The **UPDATE** statement allows us to alter data in the table.

The basic syntax of an UPDATE query with a WHERE clause is as follows:

```mysql
UPDATE table_name
SET column1=value1, column2=value2, ...
WHERE condition;
```

You specify the column and its new value in a comma-separated list after the SET keyword.

> If you omit the WHERE clause, all records in the table will be updated!

It is also possible to UPDATE multiple columns at the same time by comma-separating them:

```mysql
UPDATE Employees 
SET Salary=5000, FirstName='Robert'
WHERE ID=1;
```

### The DELETE Statement

The **DELETE** statement is used to remove data from your table. DELETE queries work much like UPDATE queries.

For example, you can delete a specific employee from the table:

```mysql
DELETE FROM Employees
WHERE ID=1;
```

>If you omit the WHERE clause, **all** records in the table will be deleted!
>The DELETE statement removes the data from the table permanently.

### Creating a Table

The **CREATE TABLE** statement is used to create a new table.

> Creating a basic table involves naming the table and defining its columns and each column's data type.

The basic syntax for the CREATE TABLE statement is as follows:

```mysql
CREATE TABLE table_name
(
	column_name1 data_type(size),
	column_name2 data_type(size),
	column_name3 data_type(size),
	....
	columnN data_type(size)
);
```

- The **column_names** specify the names of the columns we want to create.
- The **data_type** parameter specifies what type of data the column can hold. For example, use **int** for whole numbers.
- The **size** parameter specifies the maximum length of the table's column.

#### Data Types

Data Types specify the type of data for a particular column.

The most common data types:

##### Numeric

- **INT** A normal-sized integer that can be signed or unsigned.
- **FLOAT**(M,D) - A floating-point number that cannot be unsigned. You can optionally define the display length (M) and the number of decimals (D).
- **DOUBLE**(M,D) - A double precision floating-point number that cannot be unsigned. You can optionally define the display length (M) and the number of decimals (D).

##### Date and Time

- **DATE** - A date in *YYYY-MM-DD* format.
- **DATETIME** - A date and time combination in YYYY-MM-DD HH:MM:SS format.
- **TIMESTAMP** - A timestamp, calculated from midnight, January 1, 1970
- **TIME** - Stores the time in HH:MM:SS format.

##### String Type

- **CHAR**(M) - Fixed-length character string. Size is specified in parenthesis. Max 255 bytes.
- **VARCHAR**(M) - Variable-length character string. Max size is specified in parenthesis.
- **BLOB** - "Binary Large Objects" and are used to store large amounts of binary data, such as images or other types of files.
- **TEXT** - Large amount of text data.

> Choosing the correct data type for your columns is the key to good database design.

Define it as a primary key during table creation, using the **PRIMARY KEY** keyword:

```mysql
USE minhaLandingPage;
CREATE TABLE usuarios(
	id INT AUTO_INCREMENT,
	nome VARCHAR (100),
	sobrenome VARCHAR (100),
	email VARCHAR (200),
	diretoria VARCHAR (20),
	PRIMARY KEY (id)
);
```

### NOT NULL and AUTO_INCREMENT

**NOT NULL** - Indicates that a column cannot contain any NULL value.

**AUTO_INCREMENT** - Allows a unique number to be generated when a new record is inserted into a table.

```mysql
CREATE TABLE Users (
	id int NOT NULL AUTO_INCREMENT,
	username varchar(40) NOT NULL, 
	password varchar(10) NOT NULL,
	PRIMARY KEY(id)
);
```

### Alter, Drop, Rename a Table

