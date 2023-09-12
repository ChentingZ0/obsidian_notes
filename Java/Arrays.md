Array stores multiple values in a single variable
Array needs to be declared
```java
int[] ages;
String[] name;
```
 
 To create the array, specify the number of items it will hold using `new` keyword `new`
 ```java
 int[] ages = new int[5];
```
This code creates an array of 5 integers

Assign values to array,
comma-separated list
```java
String[] names = {"A", "B", "C", "D"};
System.out.println(names[2]);
```

`length`, length of the array
```java
int[] ages = {18, 33, 24, 64, 45};
System.out.println(ages.length);
```

##### Two dimensional array
```java
int [][] sample = {{1,2,3},{4,5,6}};
```
To access an element: provide two indexes, one for the array, and another for the element inside that array.
```java
int x = sample[1][0]   
// result: 4
```
