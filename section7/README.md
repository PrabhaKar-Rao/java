# Operators and Operands in Java
### Overview
In Java programming, operators are symbols that perform operations on operands. Operands can be variables, constants, or expressions. Understanding operators and operands is crucial for writing efficient and concise code.
## Java Expressions
In Java, expressions are combinations of variables, operators, and method invocations that produce a single value. They can be as simple as a single variable or as complex as a mathematical formula.
### Arithmetic Expressions
Arithmetic expressions involve arithmetic operators (+, -, *, /, %) and operands (variables or literals) to perform mathematical calculations.
### Relational Expressions
Relational expressions compare two values using relational operators (==, !=, >, <, >=, <=) and evaluate to a boolean value (true or false).
### Logical Expressions
Logical expressions combine boolean values using logical operators (&&, ||, !) to form compound conditions.
### Assignment Expressions
Assignment expressions use the assignment operator (=) to assign a value to a variable.
### Conditional Expressions
Conditional expressions, also known as the ternary operator (?:), evaluate a boolean expression and return one of two values based on the result of the evaluation.

### Assignment Operator 
The assignment operator in Java (`=`) is used to assign a value to a variable. It is one of the most commonly used operators in Java programming.
#### Syntax
```java
variable = expression;
```
###### where :
- variable is the name of the variable to which the value will be assigned.
- expression is the value that will be assigned to the variable.
#### Example 💡
```java
public class AssignmentOperatorDemo {

    public static void main(String[] args) {
        int num1, num2, num3, num4, num5;
        num1 = num2 = num3 = num4 = num5 = 98;

        double dNum1 = 3.14;
        double dNum2 = 4.48;
        dNum1 = dNum2;
        System.out.println(dNum1); //4.48
        dNum2 = 6.58;
        System.out.println(dNum1); //4.48
    }

}
```
### Usage
- Assigning a value to a variable.
- Updating the value of a variable.
### Notes
- The assignment operator is a binary operator, meaning it requires two operands: the variable and the value to be assigned.
- It evaluates the expression on the right-hand side and assigns the result to the variable on the left-hand side.
- The data type of the variable must be compatible with the data type of the expression.
## Arithmetic Operators in Java
Arithmetic operators are used to perform basic arithmetic operations such as addition, subtraction, multiplication, and division. Java provides several arithmetic operators that allow you to perform these operations on numeric operands.
### Addition Operator (+)
The addition operator (+) is used to add two operands together.
```java
int a = 5;
int b = 3;
int result = a + b;
```
### Subtraction Operator (-)
The subtraction operator (-) is used to subtract the right operand from the left operand.
```java
int a = 10;
int b = 4;
int result = a - b; // result will be 6
```
### Multiplication Operator (*)
The multiplication operato
r (*) is used to multiply two operands.
```java
int a = 3;
int b = 4;
int result = a * b; // result will be 12
```
### Division Operator (/)
The division operator (/) is used to divide the left operand by the right operand.
```java
int a = 10;
int b = 2;
int result = a / b; // result will be 5
```
### Modulus Operator (%)
The modulus operator (%) is used to find the remainder of dividing the left operand by the right operand.
```java
int a = 10;
int b = 3;
int result = a % b; // result will be 1
```
### Increment (++) and Decrement (--) Operators
The increment (++) operator is used to increment the value of an operand by 1. The decrement (--) operator is used to decrement the value of an operand by 1.
```java
int a = 5;
a++; // Increment a by 1, now a is 6
int b = 10;
b--; // Decrement b by 1, now b is 9
```
### Unary Plus Operator in Java
The unary plus operator (+) in Java is used to indicate a positive value. It is primarily used to explicitly specify the sign of a numeric expression, although it does not change the value itself.
#### Example 💡
```java
int number = 10;
int positiveNumber = +number; // positiveNumber will be 10
```
In the above example, the unary plus operator is used to explicitly indicate that the value of number is positive. However, since number is already positive, the unary plus operator does not affect its value.

###  Unary Minus Operator in Java
The unary minus operator (-) in Java is used to negate the value of its operand. It is a unary operator because it operates on only one operand.
#### Example 💡
```java
public class Main {
    public static void main(String[] args) {
        int number = 10;
        int result = -number;

        System.out.println("Original Number: " + number); //10
        System.out.println("Negated Number: " + result);// -10
    }
}
```
### Usage 🚀
The unary minus operator is commonly used when you need to change the sign of a numeric value, for example, to convert a positive number to a negative one or vice versa.
### Notes ✍️
- The operand of the unary minus operator must be a numeric type (byte, short, int, long, float, or double).
- If the operand is an integer type (byte, short, int, long), the result will be the negation of that integer.
- If the operand is a floating-point type (float or double), the result will be the negation of that floating-point number.
## Compound Arithmetic Assignment Operators in Java
### Overview
Compound arithmetic assignment operators in Java are shorthand notation for performing arithmetic operations and assignment in a single step. They combine an arithmetic operator with the assignment operator (`=`) to modify the value of a variable. These operators are useful for simplifying and streamlining code, especially when incrementing or decrementing variables by a fixed amount.
### List of Compound Arithmetic Assignment Operators
Java supports the following compound arithmetic assignment operators :
- `+=`: Addition assignment operator
- `-=`: Subtraction assignment operator
- `*=`: Multiplication assignment operator
- `/=`: Division assignment operator
- `%=`: Modulus assignment operator
### Addition Assignment `(+=)`
The `+=` operator adds the value of the right operand to the value of the left operand and assigns the result to the left operand.
#### Example 💡
```java
int x = 5;
x += 3; // Equivalent to: x = x + 3;
System.out.println(x); // Output: 8
```
### Subtraction Assignment `(-=)`
The `-=` operator subtracts the value of the right operand from the value of the left operand and assigns the result to the left operand.
#### Example 💡
```java
int x = 10;
x -= 4; // Equivalent to: x = x - 4;
System.out.println(x); // Output: 6
```
### Multiplication Assignment `(*=)`
The `*=` operator multiplies the value of the left operand by the value of the right operand and assigns the result to the left operand.
#### Example 💡
```java
int x = 3;
x *= 2; // Equivalent to: x = x * 2;
System.out.println(x); // Output: 6
```
### Division Assignment `(/=)`
The `/=` operator divides the value of the left operand by the value of the right operand and assigns the result to the left operand.
#### Example 💡
```java
int x = 8;
x /= 2; // Equivalent to: x = x / 2;
System.out.println(x); // Output: 4
```
### Modulus Assignment `(%=)`
The `%=` operator divides the value of the left operand by the value of the right operand and assigns the remainder to the left operand.
#### Example 💡
```java
int x = 10;
x %= 3; // Equivalent to: x = x % 3;
System.out.println(x); // Output: 1
```
### Conclusion  🎉
Compound arithmetic assignment operators in Java are useful for performing arithmetic operations and assignment in a single step, making code concise and readable. They offer a convenient way to update variables based on their current values.

## Realational Operators
## Equality Operator in Java
The Equality Operator `(==)` in Java is used to compare two operands to determine if they are equal. It's important to understand how it works and its nuances to avoid unexpected behavior in your Java programs.
### Basic Usage
The Equality Operator compares the values of two operands. If the values are equal, it returns `true`; otherwise, it returns `false`. It's commonly used in conditional statements and expressions.
#### Example
```java
int a = 5;
int b = 5;

boolean resul t= a==b;
System.out.println(result); //true

String str1=new String("hello");
String str2=new String("hello");

boolean isSame = str1==str2;

System.out.println(isSame);// false
```
- When comparing reference types (objects), the Equality Operator checks if the references point to the same object in memory, not if the objects have the same values.
- In the above example, `str1` and `str2` are different objects in memory, even though they have the same value. Therefore, the result of the comparison will be `false`.
### Equality vs. Identity
- **Equality :** Compares the values of two operands.
- **Identity :** Compares the memory addresses of two operands.
### Conclusion
Understanding how the Equality Operator works in Java is crucial for writing reliable and bug-free code. Always consider the types of operands you are comparing and whether you need to check for equality or identity.
## Inequality Operator in Java
In Java, the inequality operator `!=` is used to compare two values and check if they are not equal. It returns `true` if the two values are different, and `false` if they are equal.
#### Example
```java
int a = 5;
int b = 10;

boolean result= a!=b;

System.out.println(result);// true

```
### Notes
- The inequality operator can be used with all primitive data types in Java (e.g., int, float, double, char, boolean, etc.).
- It can also be used to compare objects in Java, where it checks if the references point to different objects.
- When comparing objects, it's important to understand the difference between reference equality and object equality. For object comparison, you might need to override the `equals()` method.

## Comparison Operators in Java
In Java, comparison operators are used to compare two values. These operators return a boolean value (`true` or `false`) based on the comparison result. Here, we'll discuss the greater than (`>`), greater than or equal to (`>=`), less than (`<`), and less than or equal to (`<=`) operators.

### Greater Than (`>`) Operator
The greater than operator (`>`) is used to check if the value on the left side of the operator is greater than the value on the right side.

#### Example
```java
int a = 5;
int b = 3;

Systsem.out.println(a > b); // true
```
### Greater Than or Equal To (`>=`) Operator
The greater than or equal to operator (`>=`) is used to check if the value on the left side of the operator is greater than or equal to the value on the right side.
#### Example
```java
int a = 5;
int b = 5;

System.out.println(a >= b); // Output: true
```
### Less Than (`<`) Operator
The less than operator (`<`) is used to check if the value on the left side of the operator is less than the value on the right side.
#### Example 
```java
int a = 3;
int b = 5;

System.out.println(a < b); // Output: true
```
### Less Than or Equal To (`<=`) Operator
The less than or equal to operator (`<=`) is used to check if the value on the left side of the operator is less than or equal to the value on the right side.
#### Example
```java
int a = 5;
int b = 5;

System.out.println(a <= b); // Output: true
```
## Logical Operators

### Logical NOT  Operator
The logical NOT operator (`!`) is used to invert the value of a boolean expression. It returns `true` if the operand is `false`, and false if the operand is true. Here's an example :
#### Example
```java
public class LogicalOperatorsDemo {

    public static void main(String[] args) {

        boolean isValid;
        isValid = !true; //false
        isValid = !false; // true
        int num1 = 9;
        int num2 = 6;
        isValid = ! (num1>num2); // false
    }
}
```
## Logical AND (`&&`) Operator 
The logical AND (`&&`) operator returns `true` if both operands are `true`, otherwise it returns `false`. However, if the first operand evaluates to `false`, the second operand is not evaluated because the result will always be `false` regardless of its value.
#### Example 
```java
public class LogicalOperatorsDemo {

    public static void main(String[] args) {

        boolean isValid;
        isValid = !true;
        isValid = !false;
        int num1 = 9;
        int num2 = 6;
        isValid = ! (num1>num2);

        boolean a = (num1>5) && ((num2=16)>15);
        System.out.println(a); // true
        System.out.println(num2); // 16
    }

}
```
### Logical OR (`||`) Operator
The logical OR (`||`) operator returns true if at least one of the operands is true. Similar to the logical AND operator, the logical OR operator also short-circuits the evaluation of an expression. If the first operand evaluates to true, the second operand is not evaluated because the result will always be true regardless of its value.
#### Example
```java
public class LogicalOperatorsDemo {

    public static void main(String[] args) {

        boolean isValid;
        isValid = !true;
        isValid = !false;
        int num1 = 9;
        int num2 = 6;
        isValid = ! (num1>num2);

        boolean a = (num1>10) && ((num2=16)>15);
        System.out.println(a);
        System.out.println(num2);

        boolean b = (num1 < 10) || ((num2=18)>15);
        System.out.println(b); //true
        System.out.println(num2);// 6

    }

}
```
## Logical XOR Operator 
The `XOR` operator, denoted by the caret symbol `^`, is a binary operator that returns true if and only if the operands differ. It returns false if both operands are the same.
#### Example
```java
public class LogicalOperatorsDemo {

    public static void main(String[] args) {

        boolean isValid;
        isValid = !true;
        isValid = !false;
        int num1 = 9;
        int num2 = 6;
        isValid = ! (num1>num2);

        boolean a = (num1>10) && ((num2=16)>15);
        System.out.println(a);
        System.out.println(num2);

        boolean b = (num1 < 10) || ((num2=18)>15);
        System.out.println(b);
        System.out.println(num2);

        boolean c = (num1>5) ^ (num2<10);
        System.out.println(c);// false

        boolean d = (num1>5) ^ (num2>10); true
    }
}
```

























