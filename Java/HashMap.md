Hashing: A key's informational content is used to determine a unique value called a hash code. 
Each element in the HashSet is associated with its unique hash code.

HashMap is used for storing data collections as key-value pairs. One object is used as a key(index) to another object(value).

`put`,`remove`,`get` methods are used to add, delete, access values in the HashMap.
```java
import java.util.HashMap;
public class MyClass{
	public static void main(String[] args){
	HashMap<String, Integer> points = new HashMap<String, Integer>();
	points.put("Amy", 154);
	points.put("Dave", 42);
	points.put("Rob", 733);
	System.out.println(points.get("Dave"));
	}
}
```

### HashSet
Have no duplicate values
HashSet does not retain order
```java
import java.util.HashSet; class A { public static void main(String[ ] args) { HashSet<String> set = new HashSet<String>(); set.add("A"); set.add("B"); set.add("C"); System.out.println(set.size()); } }
```