# Exception handling using try, catch and finally
In Java, an exception is an event that disrupts the normal flow of a program's instructions during execution. When an exceptional condition occurs, the Java runtime creates an exception object, which contains information about the error, such as its type and the state of the program when the error occurred. This exception object is then "thrown" from the point in the code where the error occurred, and the runtime searches for an exception handler that can handle it.

There are two main types of exceptions in Java: checked exceptions and unchecked exceptions. Checked exceptions are exceptions that must be either caught or declared to be thrown by the method in which they may occur. Unchecked exceptions, on the other hand, are exceptions that do not need to be explicitly caught or declared, and they typically indicate programming errors or other exceptional conditions that are beyond the control of the program.

Java provides a robust exception handling mechanism through the use of try-catch blocks, where code that may throw exceptions is enclosed in a try block, and any exceptions that are thrown are caught and handled by catch blocks. Additionally, Java allows for the use of finally blocks to execute cleanup code regardless of whether an exception is thrown or not. This combination of try, catch, and finally blocks provides a powerful mechanism for managing exceptional conditions in Java programs.

## Exception Hierarchy 
Throwable:

- **Error :** Represents serious problems that are typically beyond the control of the application, such as OutOfMemoryError or StackOverflowError. Usually, it is not appropriate for applications to catch or handle Error instances.
- **Exception :** Represents exceptional conditions that a program should catch and handle. This is further divided into:
- **Checked Exceptions (Compiletime Exceptions) :** These are exceptions that must be either caught or declared in the method's throws clause. They are subclasses of Exception but not of RuntimeException.
- **Unchecked Exceptions (RuntimeExceptions) :** These are exceptions that don't need to be caught or declared. They typically represent programming errors or other conditions that are beyond the control of the program. They are subclasses of RuntimeException.
### Checked Exceptions:

- **IOException :** Represents an error occurred during I/O operations.
- **FileNotFoundException :** Indicates that a file could not be found.
- **EOFException :** Indicates that the end of a file or stream has been reached unexpectedly.
- **SQLException :** Indicates an error occurred while accessing a database.
- **ClassNotFoundException :** Indicates that a class could not be found during runtime.
And many more...
### Unchecked Exceptions (RuntimeExceptions):

- **ArithmeticException :** Indicates that an arithmetic operation has failed.
- **NullPointerException :** Indicates an attempt to access or invoke a method on a null object.
- **ArrayIndexOutOfBoundsException :** Indicates that an array has been accessed with an illegal index.
- **IllegalArgumentException :** Indicates that a method has been passed an illegal or inappropriate argument.
- **IllegalStateException :** Indicates that the application is in an inappropriate state for the requested operation.
- **ClassCastException :** Indicates an invalid cast operation.
And many more...
### Example with try, catch block
```java
package com.eazybytes.exception;

import java.util.InputMismatchException;
import java.util.Scanner;

public class ExceptionDemo {

    public static void main(String[] args) {
        Scanner scanner = null;
        try {
             scanner = new Scanner(System.in);
            System.out.println("Enter a number....");
            int number = scanner.nextInt();
            System.out.println(number);
        }
        catch(Exception ex) {
            System.out.println("Please provide input in numerical format only and try again...");
        }
    }
}
```
### ArrayIndexOutofBoundsException 
`ArrayIndexOutOfBoundsException` is a runtime exception in Java that occurs when you try to access an index that is outside the bounds of an array. For example, if you have an array with 5 elements and you try to access the 6th element, it will throw `ArrayIndexOutOfBoundsException`.
```java
package com.eazybytes.exception;

import java.util.logging.Logger;

public class ArrayIndexOutofBoundsExceptionDemo {

    private static Logger logger = Logger.getLogger(
            ArrayIndexOutofBoundsExceptionDemo.class.getName());

    public static void main(String[] args) {
        try {
            int[] numbers = {1,2,3,4,5};
            System.out.println(numbers[5]);
        } catch (Exception ex) {
            logger.severe("Invalid Array index. Please try again with a valid index number");
        }

    }
}
```
### With Multipple catch blocks
```java
package com.eazybytes.exception;

import java.io.IOException;
import java.util.InputMismatchException;
import java.util.logging.Logger;

public class MultipleCatchDemo {

    private static Logger logger = Logger.getLogger(
            MultipleCatchDemo.class.getName());

    public static void main(String[] args) {
        String input = null;
        try {
                input = "Madan";
                input = input.toUpperCase();
                logger.info(input);
                input = input.substring(1,10);
            logger.info(input);
        } catch (NullPointerException ex) {
            logger.severe("An null pointer exception occurred. Please check your data");
        } catch (StringIndexOutOfBoundsException | ArrayIndexOutOfBoundsException  ex) {
            logger.severe("IndexOutOfBoundsException exception occurred. Please check your input data");
        } catch (Exception ex) {
            logger.severe("An exception occurred. Please check your program");
        }
    }
}
```
### finally block
In Java, the `finally` block is used to define a block of code that will be executed after a `try` block has completed execution, whether an exception is thrown or not. This block ensures that certain cleanup or finalization tasks are performed, such as closing resources like files or database connections.
### Syntax
```java
try {
    // Code that may throw an exception
} catch (Exception e) {
    // Exception handling code
} finally {
    // Code to be executed regardless of whether an exception is thrown or not
}
```
- The `try` block contains the code that may throw an exception.
- The `catch` block is optional and is used to handle exceptions.
- The `finally` block contains the code that will be executed regardless of whether an exception occurs or not.
#### Example
```java








