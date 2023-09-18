Java API provides a `Collection` class, included in the java.util package.

`Collection` class methods ->
`sort()`,`max()`,`min`,`reverse()`,`shuffle`.

Collections class are static, don't need a Collections object to call them.

```java
public class MyClass { public static void main(String[ ] args) { ArrayList<String> animals = new ArrayList<String>(); animals.add("tiger"); animals.add("cat"); animals.add("snake"); animals.add("dog"); Collections.sort(animals); System.out.println(animals); } }
```
