#### NULL
```sql
SELECT * FROM Customers
WHERE age IS NULL
/WHERE age IS NOT NULL
```

#### DISTINCT
Remove the duplicates using the DISTINCT keyword
DISTINCT keyword is placed before the column name we want to select
```sql
SELECT DISTINCT city
FROM Customers
```

#### Creating Tables
Data types:

**INT** - whole number

**FLOAT** - floating point number

**DOUBLE** - A double precision floating-point number.

**DATE** - A date in YYYY-MM-DD format.

**DATETIME** - A date and time combination in YYYY-MM-DD HH:MM:SS format.

**TIMESTAMP** - A timestamp, calculated from midnight, January 1, 1970

**TIME** - Stores the time in HH:MM:SS format.

**VARCHAR**(M) - Variable-length character string. Max size is specified in parenthesis.

**TEXT** - Large amount of text data.

#### Create Table
```sql
CREATE TABLE Customers(
	id INT,
	firstname VARCHAR(128),
	lastname VARCHAR(128),
	salary INT
	city VARCHAR(128)
);
```

##### DEFAULT keyword
```sql
...
salary INT DEFAULT 1000
...
```

##### NULL keyword
```sql
...
firstname VARCHAR(128) NOT NULL
...
```

#### Insert Data
When the table is created, it is empty
We can insert data using the INSERT command
```sql
INSERT INTO Customers 
VALUES (1, 'john', 'Smith', 'New York', 5000)
```


We can also insert values for specific columns only, the other columns will take the default values
```sql
INSERT INTO Customers(id, firstname, lastname, city)
VALUES
(1, 'John', 'Smith', 'New York')
```
(The INSERT query will result in an error if trying to skip a column which does not have a default value and is NOT NULL)


Insert multiple rows, by separating them commas
```sql
INSERT INTO Customers(id, firstname, lastname, city, salary)
VALUES
(1, 'John', 'Smith', 'New York', 5000),
(2, 'David', 'Williams', 'Los Angeles', 4200),
(3, 'Chloe', 'Anderson', 'Chicago', 6500);
```

#### UPDATE
To change values in a table 
```sql
UPDATE Customers
SET salary = 9900, city = 'New York'
WHERE id = 2
```
If you omit the WHERE clause, all records will be updated

#### DELETE
DELETE command is used to delete rows from a table
```sql
DELETE FROM Customers
WHERE ID = 4
```

#### ALTER & DROP
ALTER TABLE command is used to add, delete, or modify columns in an table
```sql
ALTER TABLE Customers
ADD age INT
```

#### DROP
Drop command is used to delete an entire column
```sql
ALTER TABLE Customers
DROP COLUMN city
```
#### Rename
Rename a column
```sql
ALTER TABLE Customers
RENAME city TO location
```

Rename an existing table
```sql
ALTER TABLE Customers
RENAME TO People
```

Delete  an entire table
```sql
DROP TABLE Customers
```
