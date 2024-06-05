# SQL NULL Values

##  What is a NULL Value?

A field with a `NULL` value is a field with no value.

If a field in a table is optional, it is possible to insert
a new record or update a record without adding a value to
this field. Then, the field will be saved with a `NULL` value.

```text

Note: 
-----

A NULL value is different from a zero value or a field that 
contains spaces. 

A field with a NULL value is one that has been left blank 
during record creation !
```

##  How to Test for NULL Values?

It is `NOT possible` to test for `NULL` values with comparison
operators, such as `=`, `<`, or `<>.`

We will have to use the `IS NULL` and `IS NOT NULL` operators
instead.

##  IS NULL Syntax

```sql
SELECT column_names
FROM table_name
WHERE column_name IS NULL;
```

## IS NOT NULL Syntax

```sql
SELECT column_names
FROM table_name
WHERE column_name IS NOT NULL;
```

##  Demo Database

Below is a selection from the Customers table used in the
examples:

##  The IS NULL Operator

The `IS NULL` operator is used to test for empty values
(NULL values).

The following SQL lists all customers with a NULL value in the
"Address" field:

```sql
SELECT CustomerName, ContactName, Address
FROM Customers
WHERE Address IS NULL;
```

```text
Tip: Always use IS NULL to look for NULL values.
```

##  The IS NOT NULL Operator

The `IS NOT NULL` operator is used to test for non-empty
values (NOT NULL values).

The following SQL lists all customers with a value in the
"Address" field:

```sql
SELECT CustomerName, ContactName, Address
FROM Customers
WHERE Address IS NOT NULL;
```
