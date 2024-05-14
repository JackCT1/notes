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

```
SELECT * FROM table;
```

To select specific columns from a table,

```
SELECT column1, column2 FROM table;
```

To order rows by the value of a specific column ascending or descending,

```
SELECT column1 FROM table ORDER BY column2 ASC/DESC;
```

### Aliases

```
SELECT column1 AS c1 from table;
```

## Filters

### Comparison Operators

```
SELECT c1 from t1 WHERE c1 > number;
```

```
SELECT c1 from t1 WHERE c1 != 'string';
```

### Text Operators

```
SELECT c1 from t1 WHERE c1 LIKE 'A%' OR c1 LIKE '%Z';
```

```
SELECT c1 from t1 WHERE c1 LIKE 'A%' OR c1 LIKE '_ord';
```

### Other Operators

```
SELECT c1 from t1 WHERE c1 BETWEEN number1 AND number2;
```

```
SELECT c1 from t1 WHERE c1 IS NOT NULL;
```

```
SELECT c1 from t1 WHERE id IN (1, 2, 3, 4);
```

## Subqueries

### Single Value

```
SELECT c1 FROM t1 WHERE c2 = (SELECT c2 FROM t1 WHERE COMPARiSON);
```

### Multiple Value

```
SELECT c1 FROM t1 WHERE c2 IN (SELECT c2 FROM t1 WHERE COMPARiSON);
```

### Correlated

## Joins

### Inner Join

```
SELECT table1.column1, table2.column2 FROM table1 (INNER) JOIN table2 ON table1.id = table2.id;
```

### Left Join

```
SELECT table1.column1, table2.column2 FROM table1 LEFT JOIN table2 ON table1.id = table2.id;
```

### Right Join

```
SELECT table1.column1, table2.column2 FROM table1 RIGHT JOIN table2 ON table1.id = table2.id;
```

### Full Join

```
SELECT table1.column1, table2.column2 FROM table1 FULL (OUTER) JOIN table2 ON table1.id = table2.id;
```

## Aggregates

- AVG()
- COUNT()
- SUM()
- MIN()
- MAX()

## Set Operations

### Union

### Intersect

### Except

## Window Functions

## Views
