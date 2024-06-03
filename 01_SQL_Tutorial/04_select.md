#  SQL SELECT Statement

##  The SQL SELECT Statement

The `SELECT` statement is used to select data from a database.

> Return data from the Customers table:

```sql
SELECT CustomerName, City FROM Customers;
```

##  Syntax

```sql
SELECT column1, column2, ...
FROM table_name;
```

- Here, column1, column2, ... are the field names of the table
you want to select data from.

- The table_name represents the name of the table you want to
  select data from.

## Select ALL columns

If you want to return all columns, without specifying every column
name, you can use the `SELECT *` syntax:

Example: Return all the columns from the Customers table:

```sql
SELECT * FROM Customers;
```
