# Accept input using BufferedReader and Scanner 
## Understanding System.out.println()
In Java, `System.out.println()` is a method used to print data to the standard output stream, typically the console. It belongs to the `java.io.PrintStream` class and is widely used for debugging, logging, and displaying information to the user.
### Syntax
The syntax of `System.out.println()` is as follows
```java
System.out.println(data);
```
Here, data can be of any primitive `data` type or an object. Multiple parameters can also be passed, which are automatically converted to strings and then printed.
#### Example
```java
public class HelloWorld {
    public static void main(String[] args) {
        int number = 10;
        String message = "Hello, world!";
        
        // Printing integer variable
        System.out.println("The number is: " + number);
        
        // Printing string variable
        System.out.println(message);
        
        // Printing multiple variables
        System.out.println("Number: " + number + ", Message: " + message);
    }
}
```
```java
The number is: 10
Hello, world!
Number: 10, Message: Hello, world!
```
#### Key Points
- `System.out.println()` automatically adds a newline character after printing the data.
- It can be used with any primitive data type or object.
- The method is overloaded to handle different types of parameters.
- It's commonly used for debugging purposes to print variable values and messages.
### Conclusion
Understanding `System.out.println()` is fundamental to Java programming. It's a versatile method for printing data to the console and is essential for debugging and communicating with the user.
## System.in.read()
`System.in.read()` is a method in Java that reads a single byte of data from the standard input stream (`System.in`). It primarily reads bytes of data, making it suitable for handling low-level input operations. This method can be useful in scenarios where more sophisticated input handling, such as reading strings or other data types, is not required.
### Syntax
```java
public static int read() throws IOException
```
#### Example
```java
package com.eazybytes.input;

import java.io.IOException;

public class JavaBasicInputDemo {

    public static void main(String[] args) throws IOException {
        System.out.println("Please enter a value...");
        int num = System.in.read();
        System.out.println("The user entered a value: "+ num); // It will display the ASCII value of entered number
    }

}
```
### Return Value
- Returns the next byte of data from the input stream as an integer in the range 0 to 255. If the end of the stream has been reached, the value -1 is returned.
### Exceptions
- IOException - If an I/O error occurs.
### Notes
- This method reads only one byte at a time, making it suitable for handling raw byte input. For reading characters or strings, consider using higher-level input operations provided by classes like `Scanner` or `BufferedReader`.
- Since `System.in.read()` reads bytes, it may not handle multibyte characters correctly in all cases, especially when dealing with character encodings beyond the ASCII range.
- Always wrap the call to `System.in.read()` within a try-catch block to handle any potential I/O errors.
## BufferedReader
BufferedReader is a class in Java that reads text from a character-input stream, buffering characters so as to provide for the efficient reading of characters, arrays, and lines.
#### Example
```java





