Java is a multi-threaded programming language. 

This means that our program can make optimal use of available resources by running two or more components concurrently, with each component handling a different task.

![thread](https://lecontent.sololearn.com/material-images/f2e895bb8dfd4782b1019cd75420165f-2880.png)

**Way 1**: Create a thread by extending the Thread class
1. Extend the Thread class
2. create a new object of the class and call it's **start()** method to run the thread.
```java
class A extends Thread{
	public void run(){
		System.out.println("Hello");
	}
	public static void main(String[] args){
		A object = new A();
		object.start();
	}
}
```

**Way 2**: Implementing the Runnable interface.
1. Implement the `run()` method. 
2. Create a new Thread object, pass the Runnable class to its constructor
3. Start the Thread by calling the `start()` method.
```java
class Loader implements Runnable{
	public void run(){
		System.out.println("Hello");
	}
}

class MyClass{
	public static void main(String[] args){
	Thread t = new Thread(new Loader());
	t.start();
	}
}
```


- Every Java thread is prioritized to help the operating system determine the order in which to schedule threads. 

- The priorities range from 1 to 10, with each thread defaulting to priority 5. You can set the thread priority with the **setPriority()** method.
- The **Thread.sleep()** method pauses a Thread for a specified period of time. Calling **Thread.sleep(1000)** pauses the thread for one second.