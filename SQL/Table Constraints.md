##### **`id` -> identity**

`AUTO_INCREMENT` -> create a column that automatically incremented with each new row
starts with value 1

Example:
```SQL
CREATE TABLE Customers(
	id INT NOT NULL AUTO_INCREMENT
	firstname varchar(255),
	lastname varchar(255)	
);
```

After that, when inserting new row,
the id will automatically incremented
```SQL
INSERT INTO Customers(firstname, lastname, city, age)
VALUES
('demo', 'demo', 'Paris', 52),
('test', 'test', 'London', 21);
```

starting value can be changed
```SQL
ALTER TABLE Customers
AUTO_INCREMENT = 555
```

##### Primary Key
keys are used to define relationships between tables
```SQL
CREATE TABLE Customers(
	id int NOT NULL AUTO_INCREMENT,
	firstname VARCHAR(255),
	lastname VARCHAR(255),
	PRIMARY KEY (id)
);
```
Rules for primary keys:
1. must contain **unique** values
2. cannot have **NULL** values
3. A table can only have one primary key


##### Foreign Key
Foreign key is a column in one table that refers to the Primary key in another table

```SQL
CREATE TABLE PhoneNumbers(
	id int NOT NULL AUTO_INCREMENT,
	customer_id int NOT NULL
	number varchar(55), 
	type varchar(55),
	PRIMARY KEY(id)
	FOREIGN KEY(customer_id) REFERENCES Customers(id)
)
```
In this case, **customer_id** column in the PhoneNumbers table is the foreign key which refers to the primary key **id** in the Customers table.


##### UNIQUE
A primary key constraint automatically has a **UNIQUE** constraint.
```SQL
ALTER TABLE Customers
ADD UNIQUE(lastname)
```

#### SELECT Multiple Tables
select data from multiple tables
```sql
SELECT firstname, lastname, city, number, type
FROM Customers, PhoneNumbers
WHERE Customers.id = PhoneNumbers.customer_id
```
Combine only those rows that have the corresponding customer_id

