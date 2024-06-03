# SQL BACKUP DATABASE for SQL Server

##  The SQL BACKUP DATABASE Statement

The `BACKUP DATABASE` statement is used in SQL Server
to create a full back up of an existing SQL database.

```sql
BACKUP DATABASE databasename
TO DISK = 'filepath';
```

##  The SQL BACKUP WITH DIFFERENTIAL Statement

A differential back up only backs up the parts of the database
that have changed since the last full database backup.

```sql
BACKUP DATABASE databasename
TO DISK = 'filepath'
WITH DIFFERENTIAL;
```

##  BACKUP DATABASE Example

The following SQL statement creates a full back up of
the existing database "testDB" to the D disk:

```sql
BACKUP DATABASE testDB
TO DISK = 'D:\backups\testDB.bak';
```

**Tip:**

- Always back up the database to a different drive than the actual database.
- Then, if you get a disk crash, you will not lose your backup file along with the database.

##  BACKUP WITH DIFFERENTIAL Example

The following SQL statement creates a differential back up of the database
"testDB":

```sql
BACKUP DATABASE testDB
TO DISK = 'D:\backups\testDB.bak'
WITH DIFFERENTIAL;
```

**Tip:** A differential back up reduces the back up time (since only the changes are backed up).
