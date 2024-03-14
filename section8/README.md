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


