`java.io` package includes a `File` class that allows you to work with files.

```java
import java.io.File;
...
File file = new File(" ../.../..")
```

`exist()` method can determine whether a file exists.
`getName()` method returns the name of the file.
```java
import java.io.File;
public class MyClass {
  public static void main(String[ ] args) {
    File x = new File("C:\\sololearn\\test.txt");
    if(x.exists()) {
     System.out.println(x.getName() +  "exists!");
    }
    else { 
     System.out.println("The file does not exist");
    }
  }
}
```


The **Scanner** class inherits from the **Iterator**, so it behaves like one.

We can use the Scanner object's **next()** method to read the file's contents.

The file's contents are output word by word, because the **next()** method returns each word separately.
```java
try {
  File x = new File("C:\\sololearn\\test.txt");
  Scanner sc = new Scanner(x);
  while(sc.hasNext()) {
    System.out.println(sc.next());
  }
  sc.close();
} catch (FileNotFoundException e) {
  System.out.println("Error");
}
```

### Creating Files
Formatter, another useful class in the java.util package.
```java
import java.util.Formatter;
public class MyClass {
   public static void main(String[ ] args) {
  try {
    Formatter f = new Formatter("C:\\sololearn\\test.txt");
    f.format("%s %s %s", "1","John", "Smith \r\n"); 
    f.format("%s %s %s", "2","Amy", "Brown"); 
    f.close();
  } catch (Exception e) {
      System.out.println("Error");
  }
  }
}
```

->
```java
1 John Smith
2 Amy Brown
```