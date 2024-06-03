# SQL SELECT DISTINCT Statement

##  The SQL SELECT DISTINCT Statement

The `SELECT DISTINCT` statement is used to return only
distinct (different) values.

> Select all the different countries from the "Customers" table:

```sql
SELECT DISTINCT Country FROM Customers;
```

Inside a table, a column often contains many duplicate values;
and sometimes you only want to list the different (distinct) values.

##  Syntax

```sql
SELECT DISTINCT column1, column2, ...
FROM table_name;
```

##  SELECT Example Without DISTINCT

If you omit the DISTINCT keyword, the SQL statement returns the
`Country` value from all the records of the `Customers` table:

```sql
SELECT Country FROM Customers;
```

##  Count Distinct

By using the `DISTINCT` keyword in a function called COUNT,
we can return the number of different countries.

Example:

```sql
SELECT COUNT(DISTINCT Country) FROM Customers;
```

**Note:**

- The `COUNT(DISTINCT column_name)` is not supported in Microsoft
  Access databases.

- Here is a workaround for MS Access:

```sql
SELECT Count(*) AS DistinctCountries 
FROM (SELECT DISTINCT Country FROM Customers);
```

You will learn about the `COUNT` function later in this tutorial.
