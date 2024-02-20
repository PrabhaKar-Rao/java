# Comments in Java
Comments are essential for making your code more understandable to yourself and others who might read it later. They provide context, explanations, and documentation for your code.
## Types of Comments
### Single Line Comments
Single line comments start with `//` and are used for short explanations.
```java
public class SingleLineCommentDemo {

    int age; // Represent the age of the Customer

    // Maximum number of login retry attempts allowed
    static final int MAX_RETRY_ATTEMPTS = 3;

    // main method is used to start the Java program
    public static void main(String[] args) {

        // Y indicates YES
        char y = 'Y';
        // N indicates NO
        char n = 'N';

        sum(12, 8);

    }

    public static void sum (int num1, int num2){
        int num3 = num1 + num2;
        // System.out.println(num3);
    }

}
```
### Multi-line Comments
Multi-line comments are enclosed within `/* */` and are useful for longer explanations or commenting out blocks of code.

