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
#### Example 
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



