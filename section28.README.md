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

