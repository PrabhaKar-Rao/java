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
```java
public class MultiLineCommentsDemo {

    /*
        Based on business requirements, the end user is
        allowed to retry a maximum of 3 login attempts.
        Using the below constant, the same is going to be
        controlled. If the requirement changes, then change
        the below value
     */
    static final int MAX_RETRY_ATTEMPTS = 3;

    public static void main(String[] args) {
        MultiLineCommentsDemo obj = new MultiLineCommentsDemo();
        double totalArea = obj.calculateRectangleArea(24.5, 34.6);
        System.out.println(totalArea);
    }

    /*
    This method calculates the area of the rectangle based
     on given length and width. The logic it is going to have
     is multiply two given input method arguments and return
     the same to the caller
     */
     public double calculateRectangleArea (double length, double width) {
        return length*width;
    }

}
```
### Javadoc Comments
Javadoc comments start with `/**` and are used to generate documentation for your code.

