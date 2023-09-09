`--`to add a comment in SQL
```sql
-- extracts movie titles

SELECT title

FROM movies
```

```sql
/* 
Comments with multiple lines
...
*/
```

#### ORDER BY
(ascending order by default) 
```sql
SELECT *
FROM movies
ORDER BY year
```

```sql
SELECT *
FROM customers
ORDER BY age DESC
```
Sort data by field that contains text. The default ascending order for text is alphabetical order
```sql
ant, cat, dog: ASC
```

#### LIMIT
```sql
SELECT *
FROM employees
ORDER BY salary DESC
LIMIT 10
```

#### OFFSET
```sql
SELECT title
FROM movies
LIMIT 3 OFFSET 2
```
![OFFSET](https://lecontent.sololearn.com/material-images/d7120b3b2d334150bc30a0685796f1c4-2.03.11.png)

#### Calculations(AS keyword)
```sql
SELECT name, price+delivery AS TOTAL
FROM sales
```
(Give columns a temporary name or alias using AS keyword)

#### Concatenation
Joins strings together
```sql
SELECT CONCAT(first_name, last_name)
FROM employees
```

#### WHERE 
conditional query, filtering data
```sql
SELECT title
FROM movies
WHERE year > 2000 
```

#### Special operators
not equal to `<>` can be used both numbers and string values

#### BETWEEN AND
```sql
DELET FROM products
WHERE Price BETWEEN
5 AND 9
```

#### Substring
take the first three characters from name
starting from 1, overall 3 characters
```SQL
SELECT SUBSTRING(firstname, 1, 3)
FROM Customers
```

#### REPLACE
replace all occurrences of the given string with another one in the city column
```SQL
SELECT firstname, lastname,
REPLACE(city, 'New York', 'NY')
FROM Customers
```
the change is done on the result set, and not on the actual data of the table.

#### Combine
combine multiple functions into a single query
create a new column
```SQL
SELECT CONCAT(
	SUBSTRING(firstname, 1, 1),
	'.'
	UPPER(lastname)) AS name
FROM Customers
```

