Standard Java arrays are of a fixed length, which means that after they are created, they cannot expand or shrink.

On the other hand, **ArrayLists** are created with an initial size, but when this size is exceeded, the collection is automatically enlarged.

When objects are removed, the ArrayList may shrink in size. Note that the ArrayList class is in the **java.util** package

```java
import java.util.ArrayList;
ArrayList colors = new ArrayList();
```

You can optionally specify a **capacity** and **type** of objects the ArrayList will hold: