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

#### GROUP BY
often used in conjunction with aggregate functions: SUM(), MAX()

|product_id| category    | amount |
|----------| ------------| -------|
|1         | Electronics | 500.00 |
|2         | Clothing    | 300.00 |
|3         | Electronics |  750.00|
|4         | Clothing    |  200.00|
|5         | Electronics |  600.00|

```sql
SELECT category, SUM(amount) AS total_sales_amount
FROM sales
GROUP BY category;
```

| category    | amount  |
|-------------| --------| 
| Electronics | 1850.00 |
|Clothing     |500.00   |

#### CASE
set the category columns value to 'Senior' in case the age value is greater than 65,
'Adult' in case in the range of 25 to 64,
'Youth' under 25
```SQL
SELECT firstname, lastname,
CASE
	WHEN age >= 65 THEN 'Senior'
	WHEN age >= 25 AND age < 65 THEN 'Adult'
	ELSE 'Youth'
END AS category
FROM Customers
```

`WHEN` -> condition
`THEN` -> value
`ELSE` -> other cases
`END` -> close

#### JOINS
A better way of combining data
combine multiple tables based on a condition
```
SELECT firstname, lastname, city, number, type
FROM Customers JOIN PhoneNumbers
ON Customers.id = PhoneNUmbers.customer_id
```
![join](https://lecontent.sololearn.com/material-images/61d86048b6824548b60125a41dffbc2c-2833.png)
##### set alias
To avoid long name
```SQL
SELECT C.firstname, C.lastname, C.city, PN.number, PN.type
FROM Customers AS C JOIN PhoneNumbers AS PN
ON C.id = PN.customer_id
```

By giving table aliases, use them in the query both in the selected list and in the condition

#### LEFT JOIN
Returns all rows from the left table, even no matches in the right table.
Table 1 LEFT JOIN Table 2
![leftjoin](https://lecontent.sololearn.com/material-images/ba8229c9dfda4f5da5961ceba583ae4b-2834.png)
```sql
SELECT C.firstname, C.lastname, C.city, PN.number, PN.type
FROM Customers AS C LEFT JOIN PhoneNumbers AS PN
ON C.id = PN.customer_id
```
The result contains all rows from the left table and matching data from the right table

If no match is found for a particular row, **NULL** is returned for the columns of the right table.

#### RIGHT JOIN
```sql
SELECT C.firstname, C.lastname, C.city, PN.number, PN.type 
FROM PhoneNumbers AS PN RIGHT JOIN Customers AS C 
ON C.id = PN.customer_id ORDER BY C.id
```