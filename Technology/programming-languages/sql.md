# SQL

- [Introduction](#introduction)
- [Queries](#queries)
- [Filters](#filters)
- [Subqueries](#subqueries)
- [Joins](#joins)
- [Aggregates](#aggregates)
- [Set Operations](#set-operations)
- [Window Functions](#window-functions)

## Introduction

SQL (Structured Query Language) is a tool for communicating with relational databases which store data in tables of rows and columns.

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
SELECT c1 from t1 WHERE c1 LIKE 'A%' OR c1 LIKE '';
```

### Other Operators

## Subqueries

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
