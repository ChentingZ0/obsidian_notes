### Pattern Matching
#### LIKE, %
##### (Pattern matching skills)
Used with `WHERE`command to search for patterns in string values
```sql
SELECT *
FROM comics
WHERE title LIKE 'The Avengers%'
```
May return the result like 'The Avengers: Celestial Quest ...'


`% `symbol is known as wildcard
Any number of characters(can be 0)
create patterns
eg. use patterns to extract email address that share the same domain
```sql
SELECT email
FROM users
WHERE email LIKE '%gmail.com'
```
Extract all the titles that contain the word **Avengers**
```sql
SELECT *
FROM comics
WHERE title LIKE '%Avengers%'
```

```sql
'Package%1%'
eg. Package 10E: Business Plan (right)
	Package AD1: Intermediate Plan(wrong)
```

```sql
SELECT * 
FROM products 
WHERE product_code LIKE 'A%B%'
```
#### underscore _
`_` only represent 1 single character

#### Multiple queries
can include multiple queries in SQL code. Separate them with a **semicolon(;)**
```sql
SELECT name, code 
FROM products; 

SELECT name 
FROM products 
WHERE code LIKE 'A_B_';
```

#### LOWER(), UPPER()*
**case-insensitive pattern matching**不分大小写
`LOWER（）`and `UPPRE（）`commands are used to convert strings to lower or uppercase
```sql
SELECT LOWER(title) 
FROM movies; 

SELECT UPPER(title) 
FROM movies;
```

#### Data Aggregation
##### `MAX()，MIN()`
```sql
SELECT MAX（year）
FROM movies;

SELECT MIN(year)
FROM movies;
```

##### `COUNT()` 
count the number of records
```sql
SELECT COUNT(year)
FROM movies;
```

##### `SUM()`
```sql
SELECT SUM(price)
FROM products;
```

##### `AVG`
```sql
SELECT AVG(price)
FROM products
```

#### Mixing Things Up
```sql
SELECT SUM(price+delivery) AS revenue
FROM sales
WHERE status = 'completed'
```

![example](https://lecontent.sololearn.com/material-images/1d3af3c524f84fbda87a876cdded682e-3.05.11.png)
The result is 21