# SQL

- [Overview](#overview)
- [Data Types](#data-types)
- [Operators](#operators)
- [Clauses](#clauses)
- [Indexes](#indexes)
- [Constraints](#constraints)
- [Queries](#queries)
- [Filters](#filters)
- [Subqueries](#subqueries)
- [Joins](#joins)
- [Aggregates](#aggregates)
- [Set Operations](#set-operations)
- [Window Functions](#window-functions)
- [Common Table Expressions](#common-table-expressions)
- [Views](#views)

## Overview

`SQL` (Structured Query Language) is a tool for communicating with relational databases which store data in tables of rows and columns. This communication is done via `commands`. SQL commands can be put into five categories,

### Data Definition Language (DDL)

`DDL` commands are used to define the database schema. This means they are used to create, modify, or delete the data structures (tables) rather than the data itself.

#### DDL Commands

- `CREATE` - Create database or database objects like tables
- `DROP` - Delete database objects
- `ALTER` - Change database structure
- `TRUNCATE` - Remove all records in a table
- `COMMENT` - Add comments to dictionary
- `RENAME` - Rename a database object

### Data Query Language (DQL)

`DQL` commands retrieve data from the database and can perform operations to derive insights from the data. The results are compiled into a temporary table for display.

#### DQL Commands

- `SELECT` - Retrieves data from database

### Data Manipulation Language (DML)

Similar to DDL for the database schema, `DML` commands create, update, and delete data in the database. They can insert data into tables, change change records, and delete them from tables.

#### DML Commands

- `INSERT` - Insert data into a table
- `UPDATE` - Change existing data in a table
- `DELETE` - Delete records from a table
- `LOCK` - Manages transaction concurrency (locked data can't be altered)
- `EXPLAIN PLAN` -Describe access path to data

### Data Control Language (DCL)

`DCL` is mainly focused on assigning privileges and controls to users, granting or removing them access to specific parts of the database.

#### DCL Commands

- `GRANT` - Assign privileges to a user
- `REVOKE` - Remove privileges to a user

### Transaction Control Language (TCL)

A `transaction` is an action (change) performed on the database. It is a series of tasks performed as one unit. If one task fails, the whole transaction fails.

`TCL` commands are used for managing a series of transactions.

#### TCL Commands

- `BEGIN TRANSACTION` - Start new transaction
- `COMMIT` - Save changes made during transaction
- `ROLLBACK` - Undoes changes made during transaction
- `SAVEPOINT` - Create savepoint in current transaction

![](https://media.geeksforgeeks.org/wp-content/uploads/20210920153429/new.png)

## Data Types

## Operators

## Clauses

## Indexes

## Constraints

## Queries

To select all the columns and rows from a specific table,

```sql
SELECT * FROM table;

SELECT * FROM country;
```

To select specific columns from a table,

```sql
SELECT column1, column2 FROM table;

SELECT id, name FROM city;
```

To order rows by the value of a specific column ascending or descending,

```sql
SELECT column1 FROM table ORDER BY column2 ASC/DESC;

SELECT name FROM city ORDER BY rating [ASC];
```

### Aliases

Columns and tables can be given shorthand names or aliases using the `AS` keyword.

```sql
SELECT column1 AS c1 from table;

SELECT name AS city_name FROM city;
```

```sql
SELECT t.column1 FROM table AS t;

SELECT ci.name,
FROM city AS ci;
```

## Filters

### Comparison Operators

```sql
SELECT c1 from t1 WHERE c1 > number;

SELECT name FROM city WHERE rating > 3;
```

```sql
SELECT c1 from t1 WHERE c1 != 'string';

SELECT name FROM city WHERE name != 'Berlin' AND name != 'Madrid';
```

### Text Operators

```sql
SELECT c1 from t1 WHERE c1 LIKE 'A%' OR c1 LIKE '%Z';
```

```sql
SELECT c1 from t1 WHERE c1 LIKE 'A%' OR c1 LIKE '_ord';
```

### Other Operators

```sql
SELECT c1 from t1 WHERE c1 BETWEEN number1 AND number2;

SELECT name
FROM city
WHERE population BETWEEN 500000 AND 5000000;
```

```sql
SELECT c1 from t1 WHERE c1 IS NOT NULL;

SELECT name
FROM city
WHERE rating IS NOT NULL;
```

```sql
SELECT c1 from t1 WHERE id IN (1, 2, 3, 4);

SELECT name
FROM city
WHERE country_id IN (1, 4, 7, 8);
```

## Subqueries

A `subquery` is a query that is nested inside another query

### Single Value

```sql
SELECT c1 FROM t1 WHERE c2 = (SELECT c2 FROM t1 WHERE COMPARISON);

SELECT name
FROM city
WHERE rating = (
  SELECT rating
  FROM city
  WHERE name = 'Paris'
);
```

### Multiple Value

```sql
SELECT c1 FROM t1 WHERE c2 IN (SELECT c2 FROM t1 WHERE COMPARISON);

SELECT name
FROM city
WHERE country_id IN (
  SELECT country_id
  FROM country
  WHERE population > 20000000
);
```

### Correlated

```sql
SELECT name
FROM country
WHERE EXISTS (
  SELECT *
  FROM city
  WHERE country_id = country.id
);
```

## Joins

### Inner Join

`INNER JOIN` returns only rows with matching values in the two tables.

```sql
SELECT table1.column1, table2.column2 FROM table1 (INNER) JOIN table2 ON table1.id = table2.id;

SELECT city.name, country.name
FROM city
[INNER] JOIN country
  ON city.country_id = country.id;
```

### Left Join

`LEFT JOIN` returns all rows on the left table with rows on the right table having `NULL` values if there is no match.

```sql
SELECT table1.column1, table2.column2 FROM table1 LEFT JOIN table2 ON table1.id = table2.id;

SELECT city.name, country.name
FROM city
LEFT JOIN country
  ON city.country_id = country.id;
```

### Right Join

Similar to `LEFT JOIN` only now all the rows on the right table are returned with `NULL` values on the left table for no matching rows.

```sql
SELECT table1.column1, table2.column2 FROM table1 RIGHT JOIN table2 ON table1.id = table2.id;

SELECT city.name, country.name
FROM city
RIGHT JOIN country
  ON city.country_id = country.id;
```

### Full Join

`FULL JOIN` returns all the rows from both tables with `NULL` values on either table if there is no match.

```sql
SELECT table1.column1, table2.column2 FROM table1 FULL (OUTER) JOIN table2 ON table1.id = table2.id;

SELECT city.name, country.name
FROM city
FULL [OUTER] JOIN country
  ON city.country_id = country.id;
```

### Cross Join

Cross Join returns all possible combinations of rows from the two tables.

```sql
SELECT city.name, country.name
FROM city
CROSS JOIN country;

SELECT city.name, country.name
FROM city, country;
```

### Natural Join

```sql
SELECT city.name, country.name
FROM city
NATURAL JOIN country;
```

## Set Operations

Set operations combine the results of two or more queries and return them as a single result.

### Union

Union combines the full results of two queries and removes duplicates.

```sql
SELECT name
FROM cycling
WHERE country = 'DE'
UNION / UNION ALL
SELECT name
FROM skating
WHERE country = 'DE';
```

### Intersect

Intersect only returns rows appearing in both query results.

```sql
SELECT name
FROM cycling
WHERE country = 'DE'
INTERSECT
SELECT name
FROM skating
WHERE country = 'DE';
```

### Except

Except returns rows appearing in first query but not in the second.

```sql
SELECT name
FROM cycling
WHERE country = 'DE'
EXCEPT / MINUS
SELECT name
FROM skating
WHERE country = 'DE';
```

## Aggregates

- AVG()
- COUNT()
- SUM()
- MIN()
- MAX()

## Window Functions

Window functions are similar to aggregate functions, only instead of producing a single row of results they produce a result for each row they work on. A window in this case is a set of rows.

```sql
  SELECT
    window_function() OVER(
         PARTITION BY partition_expression
         ORDER BY order_expression
         window_frame_extent
    ) AS window_column_alias
    FROM table_name
```

### Ranking Window Functions

- `ROW_NUMBER()` - Assigns sequential integer to each row in a partition. (Not repeated)
- `RANK()` - Assigns rank number to each row. Tied ranks share same rank.
- `DENSE_RANK()` - Similar to rank (tied are shared) but consecutive numbers used.
- `PERCENT_RANK` -
- `CUM_DIST()` -

### Value Window Functions

- `FIRST_VALUE()` -
- `LAST_VALUE()` -

### Aggregate Window Functions

## Common Table Expressions

Common table expressions (or CTE's) are a way to store and reuse query results. More specifically, they are virtual tables that have been labelled to then be referenced in subsequent queries, therefore simplifying them.

```sql
WITH cte AS (
  SELECT c1, c2, c3
  FROM t1
)
SELECT c1, c2
FROM cte
WHERE ....
```

## Views

Views are very similar to CTE's except that they are stored to memory (tables store data on disk) and so are database objects. By comparison a CTE is only a temporary table that must be used in a subsequent query else it is dropped. Also, a view stores the query itself, not the result of the query.

```sql
CREATE VIEW view_name AS
SELECT column1, column2.....
FROM table_name
WHERE condition;
```
