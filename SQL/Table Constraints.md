`id` -> identity

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