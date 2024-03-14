# Control Flow Statements in Java
Control flow statements in Java are used to control the execution flow of a program. They allow you to make decisions, execute code repeatedly, and branch execution based on conditions. Java provides several types of control flow statements, including:
## If-else Statements 
If-else statements are fundamental to programming as they allow you to make decisions based on certain conditions.
### Example  💡
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
### Example  💡
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
### Example  💡
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
### Advantages  🚀
- **Concise syntax :** It reduces code length compared to if-else statements, making code more readable and easier to maintain.
- **Functional programming :** It allows for functional programming-style expressions, especially when used with lambda expressions.
### Limitations  🚫
- **Readability :** Overuse or complex nesting of ternary operators can reduce code readability.
- **Limited to simple conditions :** Ternary operators are best suited for simple conditions. Complex conditions may be difficult to read or understand when expressed using the ternary operator.
### Conclusion  🎉
The ternary operator in Java provides a concise and elegant way to express conditional statements. When used appropriately, it can improve code readability and maintainability. However, it's essential to use it judiciously and avoid overcomplicating expressions.
## Switch-Case Statements
Switch-case statements in Java provide a convenient way to execute different blocks of code based on the value of a variable or expression. They offer a cleaner alternative to multiple `if-else` statements when dealing with multiple possible conditions.
### Example  💡
```java
public class SwitchCaseDemo {

    public static void main(String[] args) {

        String fruitName = "Banana";

        switch (fruitName) {

            case "Banana":
            case "Apple":
                System.out.println("$ 1.0 charged");
                break;
            case "Grapes":
                System.out.println("$ 2.0 charged");
                break;
            case "Pineapple":
                System.out.println("$ 2.5 charged");
                break;
            case "Mango":
                System.out.println("$ 3.0 charged");
                break;
            default:
                System.out.println("Pick a valid fruit");
                break;
                                                               // Output : $ 1.0 charged
        }

    }

}
```
- **switch :** Begins the switch statement and evaluates the expression.
- **case value :** Specifies a value to compare the expression against.
- **break :** Terminates the switch block. Without a break statement, execution will continue to the next case.
- **default :** Executes if the expression doesn't match any of the cases. It's optional but recommended for handling unexpected values.
### Key Points
- **Expression :** The variable or expression whose value is being compared against different cases. It must evaluate to a primitive type (such as int, char, or enum) or String (Java 7 and later).
- **Values :** Each case specifies a value to compare the expression against. These values must be constant expressions.
- **Execution Flow :** When a match is found, the corresponding code block executes. If there's no break, execution will continue to the next case. The default case, if present, is executed if no matches are found.
- **Break Statement :** Each case block should end with a break statement to prevent fall-through to subsequent cases.
- **Default Case :** It's good practice to include a default case to handle unexpected values gracefully.
##  Switch Expression
A switch expression is a control flow statement that evaluates an expression and selects one of several code blocks to execute, depending on the value of the expression. It's an enhanced version of the traditional switch statement found in many programming languages.
#### Example  💡
```java
public class SwitchExpressionDemo {

    public static void main(String[] args) {
        String fruitName = "Banana";
        switch (fruitName) {
            case "Banana", "Apple" -> System.out.println("$ 1.0 charged");
            case "Grapes" -> System.out.println("$ 2.0 charged");
            case "Pineapple" -> System.out.println("$ 2.5 charged");
            case "Mango" -> System.out.println("$ 3.0 charged");
            default -> System.out.println("Pick a valid fruit");
        }

        String output = switch (fruitName) {
            case "Banana", "Apple" -> "$ 1.0 charged";
            case "Grapes" -> "$ 2.0 charged";
            case "Pineapple" -> "$ 2.5 charged";
            case "Mango" -> "$ 3.0 charged";
            default -> "Pick a valid fruit";
        };

    String day = "FRIDAY";

        int numLetters = switch (day) {

            case "MONDAY", "FRIDAY", "SUNDAY" -> {
                System.out.println(6);
                yield 6;
            }
            case "TUESDAY" -> {
                System.out.println(7);
                yield 7;
            }
            case "THURSDAY", "SATURDAY" -> {
                System.out.println(8);
                yield 8;
            }
            case "WEDNESDAY" -> {
                System.out.println(9);
                yield 9;
            }
            default -> {
                System.out.println("Invalid Day");
                yield 0;
            }

        };

    }

}
```
## While Statement
In Java, the `while` statement is a control flow statement that repeatedly executes a block of code as long as a specified condition is true. It is used when the number of iterations is not known beforehand and depends on the condition being evaluated.
### Syntax
```java
```java
while (condition) {
    // Code block to be executed
}
```
- The condition is a boolean expression. If it evaluates to true, the code block inside the loop will be executed. If it evaluates to false, the loop terminates, and the program continues with the next statement after the loop.
- The code block within the curly braces {} contains the statements to be executed repeatedly.
### Example
```java










