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
        finally {
            System.out.println("finally block is being executed");
            if(scanner != null) {
                scanner.close();
            }
        }

    }

}
```
### Key Points
- The `finally` block is always executed, even if an exception is thrown.
- If an exception is thrown and caught, the `finally` block is executed after the `catch` block.
- If no exception is thrown, the `finally` block is still executed after the `try` block.
- The `finally` block is often used to perform cleanup tasks, such as closing resources opened in the `try` block.
### Best Practices
- **Resource Management :** Use the `finally` block to ensure that resources like files, database connections, or network connections are properly closed, regardless of whether an exception occurs.
- **Error Cleanup :** Perform any necessary cleanup operations in the `finally` block to leave the program or system in a consistent state, even in the event of an error.
- **Avoid Logic :** Keep the `finally` block free from complex logic to ensure that it executes quickly and reliably. Complex logic in the `finally` block can make code harder to understand and maintain.
### Try-With-Resources
Try-With-Resources is a feature introduced in Java 7 that simplifies resource management by automatically closing resources that are opened within the try block. It ensures that resources are closed properly without the need for explicit finally blocks.
#### Example
```java
package com.eazybytes.exception;

import java.util.Scanner;

public class TryWithResourcesDemo {

    public static void main(String[] args) {
        try (Scanner scanner = new Scanner(System.in)) {
            System.out.println("Enter a number....");
            int number = scanner.nextInt();
            System.out.println(number);
        } catch(Exception ex) {
            System.out.println("Please provide input in numerical format only and try again...");
        }
    }

}
```
### Advantges
**Automatic Resource Management :** With try-with-resources, resources are automatically closed after the try block, ensuring proper cleanup without the need for explicit finally blocks. This reduces the chance of resource leaks and simplifies code maintenance.

**Concise and Readable Code :** By eliminating the need for boilerplate code to close resources in finally blocks, try-with-resources leads to cleaner and more readable code. Developers can focus on the core logic of the program without getting distracted by resource management concerns.

**Improved Exception Handling :** Any exceptions thrown during the execution of the try block, as well as any exceptions thrown during resource closing, are properly handled. This simplifies error handling and makes code more robust.
## Try-with-Resources
Try-with-resources is a feature introduced in Java 7 that simplifies resource management by automatically closing resources at the end of their usage. This feature can significantly reduce the boilerplate code required for managing resources such as files, database connections, and network connections.
### How to Use Try-with-Resources

Using try-with-resources is straightforward. You declare the resources within the parentheses of the try statement. The resources must implement the `AutoCloseable` interface. Java automatically closes the resources at the end of the try block, whether an exception is thrown or not.

Here's the basic syntax:

```java
try (ResourceType1 resource1 = new ResourceType1();
     ResourceType2 resource2 = new ResourceType2();
     // Add more resources as needed
) {
    // Code that uses the resources
} catch (Exception e) {
    // Exception handling
}
```
Replace `ResourceType1`, `ResourceType2` etc., with the actual types of resources you want to manage.
#### Example
```java
package com.eazybytes.exception;

import java.util.Scanner;

public class TryWithResourcesDemo {

    public static void main(String[] args) {
        try (Scanner scanner = new Scanner(System.in)) {
            System.out.println("Enter a number....");
            int number = scanner.nextInt();
            System.out.println(number);
        } catch(Exception ex) {
            System.out.println("Please provide input in numerical format only and try again...");
        }
    }

}
```
### Benefits of Try-with-Resources
- Automatic Resource Management: Resources are automatically closed at the end of the try block, reducing the risk of resource leaks.
- Concise and Readable: Try-with-resources reduces boilerplate code, making your code cleaner and easier to understand.
- Exception Handling: Exceptions that occur during resource management are properly handled without the need for explicit finally blocks.
### Conclusion
Try-with-resources is a powerful feature in Java for managing resources efficiently and safely. By using this feature, you can simplify your code and improve its robustness by ensuring that resources are properly closed after use.
## throws Keyword
The `throws` keyword in Java is used in method declarations to indicate that the method may throw one or more specific exceptions during its execution. When a method uses `throws`, it essentially delegates the responsibility of handling the exception to the caller of the method.
### Syntax
```java
return_type method_name(parameters) throws exception_type1, exception_type2, ...
```
#### Example
```java
package com.eazybytes.exception;

public class Division {

    public double divide (String num1, String num2) throws
            NumberFormatException, ArithmeticException {
        int n1 = Integer.parseInt(num1);
        int n2 = Integer.parseInt(num2);
        return n1/n2;
    }

}

package com.eazybytes.exception;

public class ThrowsDemo {

    public static void main(String[] args) {
        Division division = new Division();
        try{
            double ouput = division.divide("4", "2");
            System.out.println(ouput);
        } catch (NumberFormatException | ArithmeticException ex) {
            System.out.println("Invalid data provided. Please provide valid numbers and try again..");
        }
    }

}
### Key Points
- The `throws` keyword is used in method declarations.
- It specifies the exceptions that a method might throw during its execution.
- The caller of the method must handle the declared exceptions using try-catch blocks or propagate them using the throws clause.
## throw Keyword
In Java, the `throw` keyword is used to explicitly throw an exception. This means that when a certain condition occurs in your program, you can use the `throw` keyword to create and throw an exception manually.
### Syntax
The syntax for using the `throw` keyword is as follows:
```java
throw throwableObject;
```
Here, `throwableObject` is the exception object that you want to throw.






 








