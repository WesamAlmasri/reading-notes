# SQL

![SQL image](https://www.blendo.co/wp-content/uploads/2017/11/sql_database_table_and_data_partitioning.jpg)

## What is SQL?

SQL, or Structured Query Language, is a language designed to allow both technical and non-technical users query, manipulate, and transform data from a relational database.

## SELECT queries

![select queries](https://camo.githubusercontent.com/386f6b27c414662c1e11f4fed7ffd6f224b8bb879f04607592ba2f9221b6c47d/68747470733a2f2f7777772e77696b6974656368792e636f6d2f7475746f7269616c732f73716c2f696d672f73716c2d696d616765732f73716c2d6c696b652d6f70657261746f722e676966)

```sql
Select query for a specific columns
SELECT column, another_column, …
FROM mytable;
```

To retrieve data from a SQL database, we need to write SELECT statements, which are often colloquially refered to as queries.

```sql
//Select query for all columns

SELECT *
FROM mytable;
```

## Queries with constraints

```sql
SELECT column, another_column, …
FROM mytable
WHERE condition
    AND/OR another_condition
    AND/OR …;
```

In order to filter certain results from being returned, we need to use a WHERE clause in the query. The clause is applied to each row of data by checking specific column values to determine whether it should be included in the results or not.

| Operator | Condition | SQL Example |
| -------- | --------- | ----------- |
| `=, !=, < <=, >, >=` | Standard numerical operators | `col_name != 4`|
| `BETWEEN … AND …` | Number is within range of two values (inclusive) | `col_name BETWEEN 3.5 AND 13.5`|
| `NOT BETWEEN … AND …` | Number is not within range of two values (inclusive) | `col_name NOT BETWEEN 3 AND 17`|
| `IN (…)` | Number exists in a list | `col_name IN (5, 7, 8)`|
| `NOT IN (…)` | Number does not exist in a list | `col_name NOT IN (13, 43, 55)`|

## Conclusion

![sql conclusion](https://hackr.io/blog/sql-cheat-sheet/thumbnail/large)