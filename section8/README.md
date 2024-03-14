# Control Flow Statements in Java
Control flow statements in Java are used to control the execution flow of a program. They allow you to make decisions, execute code repeatedly, and branch execution based on conditions. Java provides several types of control flow statements, including:
## If-else Statements 
If-else statements are fundamental to programming as they allow you to make decisions based on certain conditions.
### Example 
```java
public class FindNumber {
    public static void main(String[] args) {
        int num = 10;
        
        if (num > 0) {
            System.out.println("Number is positive");
        } else {
            System.out.println("Number is non-positive");
        }
    }
}
```
## if, else-if, else
### Example 
```java
public class FindTheDay {

    public static void main(String[] args) {
        String whatIsToday = "Monday";
      // Approach 1

        if(whatIsToday.equals("Monday")) {
            System.out.println("It is weekday");
        } else if (whatIsToday.equals("Tuesday")) {
            System.out.println("It is weekday");
        } else if (whatIsToday.equals("Wednesday")) {
            System.out.println("It is weekday");
        } else if (whatIsToday.equals("Thursday")) {
            System.out.println("It is weekday");
        } else if (whatIsToday.equals("Friday")) {
            System.out.println("It is weekday");
        } else if (whatIsToday.equals("Saturday")) {
            System.out.println("It is weekend");
        } else if (whatIsToday.equals("Sunday")) {
            System.out.println("It is weekend");
        } else {
            System.out.println("Invalid input. Please check the same");
        }

      //Approach 2

        if(whatIsToday.equals("Monday") || whatIsToday.equals("Tuesday")
         || whatIsToday.equals("Wednesday") || whatIsToday.equals("Thursday")
         || whatIsToday.equals("Friday")) {
            System.out.println("It is weekday");
        } else if (whatIsToday.equals("Saturday") || whatIsToday.equals("Sunday")) {
            System.out.println("It is weekend");
        } else {
            System.out.println("Invalid input. Please check the same");
        }

    }

}
```
## Nested If-else
```java
public class MessageForDay {

    public static void main(String[] args) {

        String dayOfWeek = "Wednesday";

        if (dayOfWeek.equals("Saturday") || dayOfWeek.equals("Sunday")) {
            System.out.println("Hooray, it's the weekend!");
            if (dayOfWeek.equals("Saturday")) {
                System.out.println("Time for a relaxing day or maybe some outdoor activities!");
            } else {
                System.out.println("Lazy Sunday vibes perfect for a cozy day indoors.");
            }
        } else {
            System.out.println("It's a weekday. Time to work or attend classes.");
            if (dayOfWeek.equals("Wednesday") || dayOfWeek.equals("Thursday")
                    || dayOfWeek.equals("Friday")) {
                System.out.println("Midweek hustle! Keep going, the weekend is approaching.");
            } else {
                System.out.println("Monday blues? Grab some coffee and power through the day!");
            }
        }

    }

}
```
##  Ternary Operator 
The ternary operator is a concise way of writing if-else statements in Java. It's also known as the conditional operator. It's a one-liner syntax that evaluates a condition and returns one of two values, depending on whether the condition is true or false.
### Example
```java
public class TernaryOperator {

    public static void main(String[] args) {
        int x = 10;
        int y;
       
        y = x > 5 ? 20 : 30;
        System.out.println(y);
        sum(x, x > 5 ? 20 : 30 );
    }

    public static void sum (int x, int y) {
        System.out.println(x+y);
    }
}
```
### Advantages
- **Concise syntax :** It reduces code length compared to if-else statements, making code more readable and easier to maintain.
- **Functional programming :** It allows for functional programming-style expressions, especially when used with lambda expressions.
### Limitations
- **Readability :** Overuse or complex nesting of ternary operators can reduce code readability.
- **Limited to simple conditions :** Ternary operators are best suited for simple conditions. Complex conditions may be difficult to read or understand when expressed using the ternary operator.
### Conclusion
The ternary operator in Java provides a concise and elegant way to express conditional statements. When used appropriately, it can improve code readability and maintainability. However, it's essential to use it judiciously and avoid overcomplicating expressions.




