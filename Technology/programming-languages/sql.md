# SQL

- [Overview](#overview)
- [Queries](#queries)
- [Filters](#filters)
- [Subqueries](#subqueries)
- [Joins](#joins)
- [Aggregates](#aggregates)
- [Set Operations](#set-operations)
- [Window Functions](#window-functions)

## Overview

SQL (Structured Query Language) is a tool for communicating with relational databases which store data in tables of rows and columns. This communication is done via commands. SQL commands can be put into five categories,

### Data Definition Language (DDL)

DDL commands are used to define the database schema. This means they are used to create, modify, or delete the data structures (tables) rather than the data itself.

### Data Query Language (DQL)

DQL commands retrieve data from the database and can perform operations to derive insights from the data. The results are compiled into a temporary table for display.

### Data Manipulation Language (DML)

Similar to DDL for the database schema, DML commands create, update, and delete data in the database. They can insert data into tables, change change records, and delete them from tables.

### Data Control Language (DCL)

DCL is mainly focused on assigning privileges and controls to users, granting or removing them access to specific parts of the database.

### Transaction Control Language (TCL)

A transaction is an action (change) performed on the database. TCL commands are used for managing a series of transactions.

## Queries

To select all the columns and rows from a specific table,

```sql
SELECT * FROM table;
```

To select specific columns from a table,

```sql
SELECT column1, column2 FROM table;
```

To order rows by the value of a specific column ascending or descending,

```sql
SELECT column1 FROM table ORDER BY column2 ASC/DESC;
```

### Aliases

Columns and tables can be given shorthand names or aliases using the `AS` keyword.

```sql
SELECT column1 AS c1 from table;
```

## Filters

### Comparison Operators

```sql
SELECT c1 from t1 WHERE c1 > number;
```

```sql
SELECT c1 from t1 WHERE c1 != 'string';
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
```

```sql
SELECT c1 from t1 WHERE c1 IS NOT NULL;
```

```sql
SELECT c1 from t1 WHERE id IN (1, 2, 3, 4);
```

## Subqueries

### Single Value

```sql
SELECT c1 FROM t1 WHERE c2 = (SELECT c2 FROM t1 WHERE COMPARiSON);
```

### Multiple Value

```sql
SELECT c1 FROM t1 WHERE c2 IN (SELECT c2 FROM t1 WHERE COMPARiSON);
```

### Correlated

## Joins

### Inner Join

`INNER JOIN` returns only rows with matching values in the two tables.

```sql
SELECT table1.column1, table2.column2 FROM table1 (INNER) JOIN table2 ON table1.id = table2.id;
```

### Left Join

`LEFT JOIN` returns all rows on the left table with rows on the right table having `NULL` values if there is no match.

```sql
SELECT table1.column1, table2.column2 FROM table1 LEFT JOIN table2 ON table1.id = table2.id;
```

### Right Join

Similar to `LEFT JOIN` only now all the rows on the right table are returned with `NULL` values on the left table for no matching rows.

```sql
SELECT table1.column1, table2.column2 FROM table1 RIGHT JOIN table2 ON table1.id = table2.id;
```

### Full Join

`FULL JOIN` returns all the rows from both tables with `NULL` values on either table if there is no match.

```sql
SELECT table1.column1, table2.column2 FROM table1 FULL (OUTER) JOIN table2 ON table1.id = table2.id;
```

### Cross Join

Cross Join returns all possible combinations of rows from the two tables.

## Set Operations

Set operations combine the results of two or more queries and return them as a single result.

### Union

Union combines the full results and removes duplicates.

### Intersect

Intersect only returns rows appearing in both query results.

### Except

Except returns rows appearing in first query but not in the second.

## Aggregates

- AVG()
- COUNT()
- SUM()
- MIN()
- MAX()

## Window Functions

Window functions are similar to aggregate functions, only instead of producing a single row of results they produce a result for each row they work on.

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

Views are very similar to CTE's except that they are stored to memory and so are database objects. By comparison a CTE is only a temporary table that must be used in a subsequent query else it is dropped. Also, a view stores the query itself, not the rsult of the query.

```sql
CREATE VIEW view_name AS
SELECT column1, column2.....
FROM table_name
WHERE condition;
```
