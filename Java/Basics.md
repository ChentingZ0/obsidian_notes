```java
class Demo{
	public static void main(string[] args){
	System.out.println("Hi there");
	}
}
```
only " " double quotation mark, not single ' '

Notes:
n Java, every line of code that can actually run needs to be inside a **class**

In Java, each application has an **entry point**, or a starting point, which is a method called **main**

#### Variable Type
##### float vs double
By default, decimal values are of type **double**
float is using less storage in the memory, but not as precise as double type.
```java
float length = 4.8f;
```

##### Char
single character
```java
char letter = 'B';
```

##### Boolean
only true or false
```java
boolean isOpen = false;
```

#### String
Adding strings together is called concatenation
```java
String firstname = 'James';
String lastname = 'Smith';
String fullname = firstname + " " + lastname
```

In Java, you need to **specify the type** of each variable when declaring it.
Java is a **case sensitive** language
(string String)

#### Multi-Line Comments
```java
/* This is 
a multiple line
comment */
```

##### increment, decrement
```java
int x = 8;
x--;
x--;
System.out.println(x);
```

```java
x += 1;
x *= 2;
```
