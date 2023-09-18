Each of the collection classes provides an **iterator()** method that returns an iterator to the start of the collection.

`hasNext` : returns if there's at least one more element.
`next()` : returns the next object and advances the iterator. returns the first element in the list.
`remove()`

```java
import java.util.Iterator;
import java.util.LinkedList;
public class MyClass {
public static void main(String[ ] args) {
LinkedList<String> animals = new LinkedList<String>();
animals.add("fox");
animals.add("cat");
animals.add("dog");
animals.add("rabbit");
Iterator<String> it = animals.iterator();
String value = it.next();
System.out.println(value);
}
// result: fox
```

Typically, iterators are used in loops.
```java
import java.util.Iterator;
import java.util.LinkedList;

public class MyClass { public static void main(String[ ] args) { LinkedList<String> animals = new LinkedList<String>(); animals.add("fox"); animals.add("cat"); animals.add("dog"); animals.add("rabbit"); Iterator<String> it = animals.iterator(); while(it.hasNext()) { String value = it.next(); System.out.println(value); } } } /* fox cat dog rabbit */
```