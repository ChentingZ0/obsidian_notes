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

##### Multiple Conditions
`&&` operator **AND**
```java
if(age > 18 && age < 50){
	System.out.println("Welcome!");
}
```
`||` operator 
```java
int age = 25;
int height = 100;
if(age > 18 || height > 150){
	System.out.println("Welcome!");
}
```
`!` operator (not)

chain multiple conditions
```java
if((country == "US" || country == "GB") && (age > 0 && age < 100)){
	System.out.println("Allowed");
}
```

##### While
Notice that the condition appears at the end of the loop, so the statements in the loop execute once before it is tested.

Even with a false condition, the code will run once.
```java
int x = 1;
do{
	System.out.println(x);
	x++;
} while(x < 5);
```
```java
while(...){
	...
}
```

##### For loop
```java
for(int x=1; x<5; x++){
	System.out.println(x);
}
```

##### break; continue
