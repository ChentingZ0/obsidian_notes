similar to C++
if else, else if
```java
int age = 25;
if(age <= 0){
	System.out.println("Error");
}
else if(age <= 16){
	System.out.println("Too Young");
}
else if(age < 100){
	System.out.println("Welcome!");
}
else{
	System.out.println("Really?")
}
```

**Switch syntax**
```java
int day = 2; 
switch(day){
	case 1: 
	System.out.println("Monday"); 
	break; 
	case 2: 
	System.out.println("Tuesday"); 
	break; 
	case 3: System.out.println("Wednesday"); 
	break; 
	default: System.out.println("Thursday");
	}
```
It is important to have a `break` statement for each case.
If no `break` appears, the program will continue to execute the next `case` in the switch, even if the value does not match the variable that is switched on.

Run this example to see what happens when there is no break in the case: