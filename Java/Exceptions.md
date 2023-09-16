`try` and `catch` keywords
```java
public class MyClass{
	public static void main(String[] args){
	try{
		int a [] = new int[2];
		System.out.println(a[5]);
	} catch(Exception e){
		System.out.println("An error occurred");
	}
	}
}
```
Notice the (**Exception e**) statement in the catch block is used to catch all possible Exceptions.

The `throw` keyword -> manually generate exceptions. 
The `throws` statement in the method definition defines the type of Exception the method can throw.


eg. IndexOutOfBoundsException, IllegalArgumentException, ArithmeticException, and so on.
```java
int div(int a, int b) throws ArithmeticException{
	if(b == 0){
		throw new ArithmeticException("Division by Zero");}
		else{
			return a/b;
		}
}
```

#### Runtime vs Checked Exceptions
There are two exception types, **checked** and **unchecked(runtime)**. 

The main difference is that checked exceptions are checked when compiled, while unchecked exceptions are checked at runtime.

eg. `Thread.sleep()` throws an **InterruptedException**. This is an example of a checked exception. Your code will not compile until you've handled the exception.

Divide by 0 is an example of unchecked exceptions.