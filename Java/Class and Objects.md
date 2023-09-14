```java
class MyClass{
	public static void main(String[] args){
		Animal dog = new Animal();
		dog.bark();
	}
}

class Animal{
	public static void bark(){
		System.out.println("wong wong!!")	
	}
}
```
`new` keyword to create an object.
dog is an object of type **Animal**.

**`public`** is an access modifier, accessible from any other class.
**`default`** accessible only by classes in the same package
**`protected`** default + subclasses can access protected methods and variables of the superclass(Inheritance)
**`private`** Accessible only within the declared class itself. Better to keep the variables within a class private.

For classes, the available modifers are public or default. For methods and attributes, all available.

#### Getters and Setters
`get` method returns its value, `set` method sets the value
Getters start with get, followed by the variable name, with the first letter of the variable name capitalized.
Setters start with set, followed by the variable name, with the first letter of the variable name capitalized.

```java
public class Vehicle{
	private String color;
// Getter
	public String getColor(){
		return color;
	}
// Setter
	public void setColor(String c){
		this.color = c;
	}
}
```

Once defined, use it in our main:
```java
public static void main(String[] args){
	Vehicle v1 = new Vehicle();
	v1.setColor("Red");
	System.out.println(v1.getColor());
}
```
Getters and setters are fundamental building blocks for encapsulation.

#### Constructors
Constructors invoked when an object is created and are used to initialize them. Provide initial values for object attributes.

A constructor name must be same as its class name
A constructor must have no explicit return type.
```java
public class Vehicle{
	private String color;
	Vehicle(){
		color = "Red";
	}
}
```
A constructor can also take parameters to initialize attributes.

The constructor is called when you create an object using the `new` keyword. A single class can have multiple constructors
```java
public class Vehicle{
	private String color;
	Vehicle(){
		this.setColor("Red");
	}
	Vehicle(String c){
		this.setColor(c);
	}

// Setter
	public void setColor(String c){
		this.color = c;
	}
}

public class Myclass{
	public static void main(String[] args){
		Vehicle v = new Vehicle("Blue");
	}
}
```

#### Value type/ Referenece type
**value types** are basic types, including byte, short, int, boolean, char ...
These data types store the values assigned to them in the corresponding memory locations.

So, when you pass them to a method, you basically operate on the variable's **value**, rather than on the variable itself.

A **reference type** stores a reference (or address) to the memory location where the corresponding data is stored.
object, Arrays, Strings are reference type

**Math** class
```java
public class MyClass{
	public static void main(String[ ] args){
	Person j; 
	j = new Person("John"); 
	j.setAge(20);
	celebrateBirthday(j); 
	System.out.println(j.getAge()); 
	} 
					 
static void celebrateBirthday(Person p){ 
	p.setAge(p.getAge() + 1);
	}
}
					}
```

#### Static
##### static variable
When you declare a variable or method as **static**, it belongs to the class rather than to a specific instance. Only one instance of a static member exists, even if you create multiple objects of the class.
```java
public class Counter {
    public static int COUNT=0;
    Counter() {
        COUNT++;
    }
}

public class MyClass {
    public static void main(String[ ] args) {
        Counter c1 = new Counter();
        Counter c2 = new Counter();
        System.out.println(Counter.COUNT);
    }
}
//result: COUNT = 2
```
**COUNT** variable will be shared by all objects of that class
Convention: use upper case when naming a static variable.

##### static method
Math class, you can call without creating a Math object
call without creating the actual object
```java
public class Vehicle{
	public static void horn(){
		System.out.println("Beep");
	}
}

public class MyClass{
    public static void main(String[ ] args) {
        Vehicle.horn();
    }
}
```
The **main** method must always be static.

#### final
`final` keyword to mark a variable constant, it can be assigned only once
```java
class MyClass{
	public static final double PI = 3.14;
	public static void main(String[] args){
		System.out.println(PI);
	}
}
```

#### Encapsulation
To achieve encapsulation in Java, declare the class variable as **private** and provide public **setter** and **getter** methods to modify the variables' values.

Variable -> private, method -> public. 

#### Inheritance
Inherits all of the superclass' **non-private** variables and methods
subclass(child class), superclass(parent class)
`extends` keyword
```java
class Dog [b]extends[/b] Animal{
// Have the class Dog to inherit from the class Animal
} 
```

```java
class Animal{
	protected int legs;
	public void eat(){
		System.out.println("Animal eats");
	}
}

class Dog [b]extends [/b]Animal{
Dogs(){
	legs = 4;
}
}
```

The constructor of the superclass is called when the subclass is instantiated.

#### Polymorphism
One method, with different implementations
```java
class Animal {
  public void makeSound() {
    System.out.println("Grr...");
  }
}
class Cat extends Animal {
  public void makeSound() {
    System.out.println("Meow");
  }
}
class Dog extends Animal {
  public void makeSound() {
    System.out.println("Woof");
  }
}
```

#### Overriding&Overloading
methods with same return type and arguments -> overriding
methods with same name, but different parameters -> overloading
A method declared **final** or **static** cannot be overridden
Constructors cannot be overridden