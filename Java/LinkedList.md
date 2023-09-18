LinkedList is better for manipulating data
In addition  to storing the object.
For a program with large numbers of inserts and deletes, it's better to use the LinkedList.
The LinkedList stores the memory address of the element that follows it. 
It's called a LinkedList because each element contains a link to the neighboring element.
![linkedlist](https://lecontent.sololearn.com/material-images/5e3b81eec9054d75846724c94f5c48c2-2443.png)
```java
LinkedList<String> c = new LinkedList<String>();
c.add("Red");

for(String s:c){
	System.out.println(s);
}
```

