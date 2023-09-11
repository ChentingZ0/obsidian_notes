Using Scanner class for taking input
State at the top of all code

Create a Scanner object(syntax)
```java
import java.util.Scanner

class Demo{
	public static void main(String[] args){
	Scanner sc = new Scanner(System.in);
	String name = sc.nextLine();
	int age = sc.nextInt();
	System.out.println("Name" + name);
	System.out.println("age" + age);
	}
}
```

