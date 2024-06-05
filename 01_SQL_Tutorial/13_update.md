# SQL UPDATE Statement

##  The SQL UPDATE Statement

The `UPDATE` statement is used to modify the existing
records in a table.

###  UPDATE Syntax

```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

```text
Note: 
-----

Be careful when updating records in a table ! 

Notice the `WHERE` clause in the `UPDATE` statement. 
The `WHERE` clause specifies which record(s) that 
should be updated. If you omit the `WHERE` clause, 
all records in the table will be updated!
```

##  Demo Database

Below is a selection from the Customers table used in the examples:

| CustomerID | CustomerName                       | ContactName        | Address                       | City        | PostalCode | Country |
|------------|------------------------------------|--------------------|-------------------------------|-------------|------------|---------|
| 1          | Alfreds Futterkiste                | Maria Anders       | Obere Str. 57                 | Berlin      | 12209      | Germany |
| 2          | Ana Trujillo Emparedados y helados | Ana Trujillo       | Avda. de la Constitución 2222 | México D.F. | 05021      | Mexico  |
| 3          | Antonio Moreno Taquería            | Antonio Moreno     | Mataderos 2312                | México D.F. | 05023      | Mexico  |
| 4          | Around the Horn                    | Thomas Hardy       | 120 Hanover Sq.               | London      | WA1 1DP    | UK      |
| 5          | Berglunds snabbköp                 | Christina Berglund | Berguvsvägen 8                | Luleå       | S-958 22   | Sweden  |

## UPDATE Table

The following SQL statement updates the first customer
(CustomerID = 1) with a new contact person and a new city.

```sql
UPDATE Customers
SET ContactName = 'Alfred Schmidt', City= 'Frankfurt'
WHERE CustomerID = 1;
```

The selection from the `Customers` table will now look like this:

| CustomerID |            CustomerName            |     ContactName    |            Address            |     City    | PostalCode | Country |
|:----------:|:----------------------------------:|:------------------:|:-----------------------------:|:-----------:|:----------:|:-------:|
| 1          | Alfreds Futterkiste                | Alfred Schmidt     | Obere Str. 57                 | Frankfurt   | 12209      | Germany |
| 2          | Ana Trujillo Emparedados y helados | Ana Trujillo       | Avda. de la Constitución 2222 | México D.F. | 05021      | Mexico  |
| 3          | Antonio Moreno Taquería            | Antonio Moreno     | Mataderos 2312                | México D.F. | 05023      | Mexico  |
| 4          | Around the Horn                    | Thomas Hardy       | 120 Hanover Sq.               | London      | WA1 1DP    | UK      |
| 5          | Berglunds snabbköp                 | Christina Berglund | Berguvsvägen 8                | Luleå       | S-958 22   | Sweden  |

## UPDATE Multiple Records

It is the `WHERE` clause that determines how many records will
be updated.

The following SQL statement will update the ContactName to `Juan`
for all records where country is "Mexico":

```sql
UPDATE Customers
SET ContactName='Juan'
WHERE Country='Mexico';
```

The selection from the "Customers" table will now look like this:

| CustomerID | CustomerName                       | ContactName        | Address                       | City        | PostalCode | Country |
|------------|------------------------------------|--------------------|-------------------------------|-------------|------------|---------|
| 1          | Alfreds Futterkiste                | Alfred Schmidt     | Obere Str. 57                 | Frankfurt   | 12209      | Germany |
| 2          | Ana Trujillo Emparedados y helados | Ana Trujillo       | Avda. de la Constitución 2222 | México D.F. | 05021      | Mexico  |
| 3          | Antonio Moreno Taquería            | Antonio Moreno     | Mataderos 2312                | México D.F. | 05023      | Mexico  |
| 4          | Around the Horn                    | Thomas Hardy       | 120 Hanover Sq.               | London      | WA1 1DP    | UK      |
| 5          | Berglunds snabbköp                 | Christina Berglund | Berguvsvägen 8                | Luleå       | S-958 22   | Sweden  |

## Update Warning

```text
Note: 
------

Be careful when updating records. If you omit the WHERE clause, 
ALL records will be updated!
```

```sql
UPDATE Customers
SET ContactName='Juan';
```

The selection from the "Customers" table will now look like this:

| CustomerID | CustomerName                       | ContactName | Address                       | City        | PostalCode | Country |
|------------|------------------------------------|-------------|-------------------------------|-------------|------------|---------|
| 1          | Alfreds Futterkiste                | Juan        | Obere Str. 57                 | Frankfurt   | 12209      | Germany |
| 2          | Ana Trujillo Emparedados y helados | Juan        | Avda. de la Constitución 2222 | México D.F. | 05021      | Mexico  |
| 3          | Antonio Moreno Taquería            | Juan        | Mataderos 2312                | México D.F. | 05023      | Mexico  |
| 4          | Around the Horn                    | Juan        | 120 Hanover Sq.               | London      | WA1 1DP    | UK      |
| 5          | Berglunds snabbköp                 | Juan        | Berguvsvägen 8                | Luleå       | S-958 22   | Sweden  |
