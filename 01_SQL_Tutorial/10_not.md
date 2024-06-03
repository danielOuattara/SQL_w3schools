# SQL NOT Operator

## The NOT Operator

The `NOT` operator is used in combination with other operators
to give the opposite result, also called the negative result.

In the select statement below we want to return all customers
that are `NOT` from Spain:

> Select only the customers that are NOT from Spain:

```sql
SELECT * 
    FROM Customers
    WHERE NOT Country = 'Spain';
```

In the example above, the `NOT` operator is used in combination
with the `=` operator, but it can be used in combination with
other comparison `and/or` logical operators.

See examples below.

##  Syntax

```sql
SELECT column1, column2, ...
    FROM table_name
    WHERE NOT condition;
```

##  Demo Database

Below is a selection from the Customers table used in the examples:
| CustomerID |            CustomerName            |     ContactName    |            Address            |     City    | PostalCode | Country |
|:----------:|:----------------------------------:|:------------------:|:-----------------------------:|:-----------:|:----------:|:-------:|
| 1          | Alfreds Futterkiste                | Maria Anders       | Obere Str. 57                 | Berlin      | 12209      | Germany |
| 2          | Ana Trujillo Emparedados y helados | Ana Trujillo       | Avda. de la Constitución 2222 | México D.F. | 05021      | Mexico  |
| 3          | Antonio Moreno Taquería            | Antonio Moreno     | Mataderos 2312                | México D.F. | 05023      | Mexico  |
| 4          | Around the Horn                    | Thomas Hardy       | 120 Hanover Sq.               | London      | WA1 1DP    | UK      |
| 5          | Berglunds snabbköp                 | Christina Berglund | Berguvsvägen 8                | Luleå       | S-958 22   | Sweden  |

## NOT LIKE

> Select customers that does not start with the letter 'A':

```sql
SELECT * 
    FROM Customers
    WHERE CustomerName NOT LIKE 'A%';
```

##  NOT BETWEEN

> Select customers with a `customerID` `not between` 10 and 60:

```sql
SELECT * 
    FROM Customers
    WHERE CustomerID NOT BETWEEN 10 AND 60;
```

##  NOT IN

> Select customers that are not from Paris or London:

```sql
SELECT * 
    FROM Customers
    WHERE City NOT IN ('Paris', 'London');
```

## NOT Greater Than

> Select customers with a CustomerId not greater than 50:

```sql
SELECT * 
    FROM Customers
    WHERE NOT CustomerID > 50;
```

```text
Note:
-----

There is a not-greater-than operator: `!>` that would give you 
the same result.
```

##  NOT Less Than

> Select customers with a CustomerID not less than 50:

```sql
SELECT * FROM Customers
WHERE NOT CustomerId < 50;
```

```text
Note: 
------

There is a not-less-than operator: `!<` that would give you 
the same result.
```
