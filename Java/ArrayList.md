Standard Java arrays are of a fixed length, which means that after they are created, they cannot expand or shrink.

On the other hand, **ArrayLists** are created with an initial size, but when this size is exceeded, the collection is automatically enlarged.

When objects are removed, the ArrayList may shrink in size. Note that the ArrayList class is in the **java.util** package

```java
import java.util.ArrayList;
ArrayList colors = new ArrayList();
```

You can optionally specify a **capacity** and **type** of objects the ArrayList will hold:
```java
ArrayList<String> colors = new ArrayList<String>(10);

```

`add()` method, `remove` method
```java
import java.util.ArrayList;

public class MyClass { public static void main(String[ ] args) { ArrayList<String> colors = new ArrayList<String>(); colors.add("Red"); colors.add("Blue"); colors.add("Green"); colors.add("Orange"); colors.remove("Green"); System.out.println(colors); } }
```
`contain()`,`get(index)`,`size()`,`clear()`

