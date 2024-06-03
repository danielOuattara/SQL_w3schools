# SQL AND Operator

## The SQL AND Operator

The `WHERE` clause can contain one or many `AND` operators.

The `AND` operator is used to filter records based on more
than one condition, like if you want to return all customers
from Spain that starts with the letter 'G':

> Select all customers from Spain that starts with the letter 'G':

```sql
SELECT *
FROM Customers
WHERE Country='Spain' AND CustomerName LIKE 'G%';
```

##  Syntax

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition1 AND condition2 AND condition3 ...;
```

##  AND vs OR

The AND operator displays a record if all the conditions are TRUE.

The OR operator displays a record if any of the conditions are TRUE.

## Demo Database

Below is a selection from the Customers table used in the examples:
| CustomerID |            CustomerName            |     ContactName    |            Address            |     City    | PostalCode | Country |
|:----------:|:----------------------------------:|:------------------:|:-----------------------------:|:-----------:|:----------:|:-------:|
| 1          | Alfreds Futterkiste                | Maria Anders       | Obere Str. 57                 | Berlin      | 12209      | Germany |
| 2          | Ana Trujillo Emparedados y helados | Ana Trujillo       | Avda. de la Constitución 2222 | México D.F. | 05021      | Mexico  |
| 3          | Antonio Moreno Taquería            | Antonio Moreno     | Mataderos 2312                | México D.F. | 05023      | Mexico  |
| 4          | Around the Horn                    | Thomas Hardy       | 120 Hanover Sq.               | London      | WA1 1DP    | UK      |
| 5          | Berglunds snabbköp                 | Christina Berglund | Berguvsvägen 8                | Luleå       | S-958 22   | Sweden  |

## All Conditions Must Be True

The following SQL statement selects all fields from `Customers` where `Country` is "Germany"
`AND` `City` is "Berlin" `AND` `PostalCode` is higher than 12000:

```sql
SELECT * FROM Customers
    WHERE Country = 'Germany'
    AND City = 'Berlin'
    AND PostalCode > 12000;
```

## Combining AND and OR

You can combine the AND and OR operators.

The following SQL statement selects all customers from Spain that starts
with a "G" or an "R".

**Make sure you use parenthesis to get the correct result.**

> Select all Spanish customers that starts with either "G" or "R":

```sql
SELECT * FROM Customers
    WHERE Country = 'Spain' 
    AND (CustomerName LIKE 'G%' OR CustomerName LIKE 'R%');
```

**Without parenthesis**, the select statement will return :

- all customers from Spain that starts with a "G",
- plus all customers that starts with an "R", regardless of the country value:

> Select all customers that either:
>
> - are from Spain and starts with either "G"
> - OR starts with the letter "R"

```sql
SELECT * FROM Customers
    WHERE Country = 'Spain' 
    AND CustomerName LIKE 'G%' 
    OR CustomerName LIKE 'R%';
```
