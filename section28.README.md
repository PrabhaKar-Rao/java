# Multithreading in Java 
Multithreading in Java refers to the ability of a Java program to execute multiple threads concurrently. A thread in Java represents an independent path of execution within a program. Multithreading allows a program to perform multiple tasks simultaneously, enhancing performance and responsiveness.

In Java, multithreading is achieved primarily by using two mechanisms:

Extending the Thread class: You can create a new class that extends the Thread class and override its `run()` method to define the code that will run concurrently. Then, you instantiate objects of this class and call their `start()` method to begin execution.

```java
class MyThread extends Thread {
    public void run() {
        // Code to be executed concurrently
    }
}
```
Implementing the Runnable interface: Alternatively, you can implement the Runnable interface, which defines a single method run(), and pass an instance of your class to a Thread object. This method is often preferred because Java doesn't support multiple inheritance, and implementing interfaces is more flexible than extending classes.

```java
class MyRunnable implements Runnable {
    public void run() {
        // Code to be executed concurrently
    }
}
```
Then, you create a Thread object and pass an instance of MyRunnable to it:

```java
MyRunnable myRunnable = new MyRunnable();
Thread thread = new Thread(myRunnable);
thread.start();
```
Multithreading allows different parts of a program to execute simultaneously, thus making the program more responsive, efficient, and capable of handling multiple tasks concurrently. However, it also introduces challenges such as synchronization and coordination between threads to avoid issues like race conditions and deadlocks. Java provides various mechanisms and classes, such as locks, mutexes, and synchronized blocks, to address these challenges and ensure safe concurrent execution.

## How Multiple Threads Improve Performance 
In Java programming, threading allows you to execute multiple tasks concurrently, thus improving performance by leveraging the computational resources more effectively. This README provides an overview of how multiple threads improve performance in Java.

### Benefits of Multithreading
- **1. Concurrency :**
Multithreading enables concurrent execution of tasks, allowing different parts of a program to run simultaneously. This concurrency leads to better resource utilization and faster execution of tasks.
- **2. Parallelism:**
With multithreading, tasks can be executed in parallel on multicore processors. This parallelism leads to significant performance improvements, especially for CPU-bound tasks.
- **3. Responsiveness :**
By offloading time-consuming tasks to separate threads, multithreading ensures that the application remains responsive to user input. This is crucial for creating interactive and user-friendly applications.
- **4. Scalability :**
Multithreading facilitates scalability by enabling the distribution of tasks across multiple threads. As the workload increases, more threads can be created to handle the additional load, resulting in better scalability.
- **5. Resource Utilization :**
Multithreading allows better utilization of system resources such as CPU and memory. By keeping the CPU busy with multiple threads, idle time is reduced, leading to improved overall performance.
- **6. Asynchronous Execution :**
Multithreading enables asynchronous execution of tasks, where a thread can continue executing other tasks while waiting for I/O operations or other blocking tasks to complete. This improves overall throughput and responsiveness.
### How to Implement Multithreading in Java
In Java, multithreading can be implemented using the Thread class or the Runnable interface. Here's a basic example using the Thread class:

```java
public class MyThread extends Thread {
    public void run() {
        // Code to be executed concurrently
    }
}

public class Main {
    public static void main(String[] args) {
        MyThread thread1 = new MyThread();
        MyThread thread2 = new MyThread();
        
        thread1.start();
        thread2.start();
    }
}
```
Alternatively, you can use the Runnable interface:

```java
public class MyRunnable implements Runnable {
    public void run() {
        // Code to be executed concurrently
    }
}

public class Main {
    public static void main(String[] args) {
        Thread thread1 = new Thread(new MyRunnable());
        Thread thread2 = new Thread(new MyRunnable());
        
        thread1.start();
        thread2.start();
    }
}
```
### Conclusion
Multithreading is a powerful technique in Java programming for improving performance and scalability. By allowing concurrent execution of tasks, multithreading maximizes CPU utilization, enhances responsiveness, and enables efficient resource utilization. When used effectively, multithreading can significantly boost the performance of Java applications.

## Creating Threads in Java
Threads in Java allow you to execute multiple tasks concurrently, improving the efficiency of your programs by leveraging the available resources. Here's a guide on how to create threads in Java:

### 1. Extending the Thread Class
You can create a thread in Java by extending the Thread class and overriding its `run()` method.

```java
public class MyThread extends Thread {
    public void run() {
        // Code to be executed in the thread
        System.out.println("Thread is running");
    }

    public static void main(String[] args) {
        MyThread thread = new MyThread();
        thread.start(); // Start the thread
    }
}
```
### 2. Implementing the Runnable Interface
Alternatively, you can implement the Runnable interface and pass it to a Thread object.

```java
public class MyRunnable implements Runnable {
    public void run() {
        // Code to be executed in the thread
        System.out.println("Thread is running");
    }

    public static void main(String[] args) {
        MyRunnable myRunnable = new MyRunnable();
        Thread thread = new Thread(myRunnable);
        thread.start(); // Start the thread
    }
}
```
### 3. Using Lambda Expressions
With Java 8 and later versions, you can use lambda expressions to define the `run()` method directly.

```java
public class Main {
    public static void main(String[] args) {
        Thread thread = new Thread(() -> {
            // Code to be executed in the thread
            System.out.println("Thread is running");
        });
        thread.start(); // Start the thread
    }
}
```
### Thread Lifecycle
Understanding the lifecycle of a thread is essential for effective thread management. The main states of a thread are:

- **New :** When a thread is instantiated.
- **Runnable :** When a thread is ready to run but waiting for CPU time.
- **Running :** When the thread is executing its task.
- **Blocked/Waiting :** When a thread is waiting for some resource.
- **Terminated :** When the thread has completed its task or terminated abruptly.
### Thread Synchronization
When multiple threads access shared resources, synchronization is essential to prevent data corruption. Java provides synchronization mechanisms like synchronized blocks and `volatile` keyword to ensure thread safety.
## Multithreading Program in Java
This Java program demonstrates a simple multithreading example where multiple threads are created to perform tasks concurrently. It illustrates basic multithreading concepts such as thread creation, synchronization, and joining threads.

### Example
Suppose we have a task of printing numbers from 1 to 10,000. We'll create multiple threads, each responsible for printing a portion of these numbers concurrently.

```java
public class Main {
    public static void main(String[] args) {
        // Create multiple threads
        Thread thread1 = new Thread(new Task(1, 2500));
        Thread thread2 = new Thread(new Task(2501, 5000));
        Thread thread3 = new Thread(new Task(5001, 7500));
        Thread thread4 = new Thread(new Task(7501, 10000));

        // Start the threads
        thread1.start();
        thread2.start();
        thread3.start();
        thread4.start();

        // Wait for all threads to finish
        try {
            thread1.join();
            thread2.join();
            thread3.join();
            thread4.join();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
    }
}
```
The Task class represents the task to print numbers within a specified range.

```java
public class Task implements Runnable {
    private int start;
    private int end;

    public Task(int start, int end) {
        this.start = start;
        this.end = end;
    }

    @Override
    public void run() {
        for (int i = start; i <= end; i++) {
            System.out.println(Thread.currentThread().getName() + ": " + i);
        }
    }
}
```
## Thread Methods in Java
### `getId()`

- **Description:** Returns the identifier of this Thread. The thread ID is a unique long value assigned to each new thread when it is created.
- **Syntax:** `public long getId()`
- **Return Type:** `long`
- **Example:**
  ```java
  Thread thread = new Thread();
  long id = thread.getId();
  System.out.println("Thread ID: " + id);
  ```
### getName()
- **Description :** Returns the name of this Thread.
- **Syntax :** public String getName()
- **Return Type :** String
### Example:
```java
Thread thread = new Thread();
String name = thread.getName();
System.out.println("Thread Name: " + name);
```
### setName()
- **Description :** Sets the name of this Thread.
- **Syntax :** public final void setName(String name)
### Parameters:
- **name :** The new name for this Thread.
### Example:
```java
Thread thread = new Thread();
thread.setName("MyThread");
currentThread();
```
- **Description :** Returns a reference to the currently executing Thread object.
- **Syntax :** public static native Thread currentThread()
- **Return Type :** Thread
### Example:
```java
Thread currentThread = Thread.currentThread();
System.out.println("Current Thread: " + currentThread.getName());
```
### sleep()
- **Description :** Causes the currently executing thread to sleep (temporarily cease execution) for the specified number of milliseconds.
- **Syntax :** public static void sleep(long millis) throws InterruptedException
### Parameters:
- **millis :** The length of time to sleep in milliseconds.
- **Throws :** InterruptedException - if any thread has interrupted the current thread.
### Example:
```java
try {
    Thread.sleep(1000); // Sleep for 1 second
} catch (InterruptedException e) {
    e.printStackTrace();
}
```

### join()
- **Description :** Waits for this thread to die.
- **Syntax :** public final void join() throws InterruptedException
- **Throws :** InterruptedException - if any thread has interrupted the current thread.
### Example:
```java
Thread thread = new Thread();
thread.start();
thread.join(); // Wait for the thread to finish execution
```
### setPriority()
- **Description :** Sets the priority of this thread.
- **Syntax :** public final void setPriority(int newPriority)
### Parameters:
- **newPriority :** The new priority for this thread. The value should be in the range 1-10.
### Example:
```java
Thread thread = new Thread();
thread.setPriority(Thread.MAX_PRIORITY); // Set priority to maximum
```
### getPriority()
- **Description :** Returns the priority of this thread.
- **Syntax :** public final int getPriority()
- **Return Type :** int
### Example:
```java
Thread thread = new Thread();
int priority = thread.getPriority();
System.out.println("Thread Priority: " + priority);
```
### wait()
- **Description :**  Causes the current thread to wait until another thread invokes the notify() method or the notifyAll() method for this object.
- **Syntax :** public final void wait() throws InterruptedException
- **Throws :** InterruptedException - if any thread interrupted the current thread before or while the current thread was waiting for a notification.
#### Example:
```java
synchronized (sharedObject) {
    sharedObject.wait(); // Wait for notification
}
```
### notify()
- **Description :** Wakes up a single thread that is waiting on this object's monitor.
- **Syntax :** public final void notify()
#### Example:
```java
synchronized (sharedObject) {
    sharedObject.notify(); // Notify a single waiting thread
}
```
### notifyAll()
- **Description :** Wakes up all threads that are waiting on this object's monitor.
- **Syntax :** public final void notifyAll()
#### Example:
```java
synchronized (sharedObject) {
    sharedObject.notifyAll(); // Notify all waiting threads
}
```

### Race Condition:
A race condition occurs in concurrent programming when the outcome of a program depends on the relative timing or interleaving of multiple threads or processes. It happens when two or more threads or processes attempt to modify shared data at the same time. The result of the program becomes unpredictable and may lead to erroneous behavior.

#### Example:
Consider a scenario where two threads, Thread A and Thread B, increment a shared counter variable:

```java
// Shared Counter
int counter = 0;

// Thread A
Thread threadA = new Thread(() -> {
    for (int i = 0; i < 1000; i++) {
        counter++;
    }
});

// Thread B
Thread threadB = new Thread(() -> {
    for (int i = 0; i < 1000; i++) {
        counter++;
    }
});

// Start both threads
threadA.start();
threadB.start();

// Wait for both threads to finish
threadA.join();
threadB.join();

// Print the final value of the counter
System.out.println("Counter: " + counter);
```
In this example, the expected final value of the counter should be 2000 (1000 increments from Thread A and 1000 increments from Thread B). However, due to the race condition, the actual final value may vary, and the program may produce unexpected results.

### Synchronization Keywords:
Java provides synchronization mechanisms to prevent race conditions and ensure thread-safe access to shared resources. Two main synchronization keywords are used: synchronized keyword and volatile keyword.

### synchronized Keyword:
The synchronized keyword is used to create synchronized blocks of code or methods.
It ensures that only one thread can execute a synchronized block or method at a time, preventing concurrent access to shared resources.
It can be applied to instance methods, static methods, and blocks of code.
### Example of synchronized method:
```java
public synchronized void incrementCounter() {
    counter++;
}
Example of synchronized block:
java
Copy code
synchronized (sharedObject) {
    // Critical section of code
}
```
### volatile Keyword:
The volatile keyword is used to indicate that a variable's value will be modified by different threads.
It ensures that changes to the variable made by one thread are immediately visible to other threads.
It does not provide atomicity like synchronized, but it ensures visibility of changes across threads.
#### Example:
```java
private volatile int sharedVariable;
```
### Conclusion:
Race conditions can lead to unpredictable behavior in concurrent programs. To avoid race conditions, synchronization mechanisms such as synchronized and volatile are used in Java to ensure thread safety and proper coordination among threads accessing shared resources. Understanding and correctly applying these synchronization keywords are essential for writing reliable and efficient concurrent programs.

