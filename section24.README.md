# Functional programming using Lambda Expressions 📚
Functional programming is a programming paradigm that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data. In functional programming, functions are first-class citizens, meaning they can be passed as arguments to other functions, returned as values from other functions, and assigned to variables.

Key concepts in functional programming include:

**Pure Functions :** Functions that produce output based only on their inputs, with no side effects. Given the same input, a pure function will always return the same output, making it easier to reason about and test.

**Immutability :** Data structures, once created, cannot be modified. Instead of changing the state of existing data, functional programming encourages creating new data structures with the desired modifications.

**Higher-order Functions :** Functions that can take other functions as arguments or return functions as results. This allows for powerful abstractions and concise code.

**Recursion :** Recursion is often used instead of looping constructs like for or while loops. Functions call themselves with modified arguments until a base case is reached.

**Referential Transparency :** The idea that an expression can be replaced with its value without changing the program's behavior. This facilitates reasoning about code and enables optimizations.

**Functional Composition :** Combining smaller functions to create larger functions, often using techniques like function composition or chaining.

**Lazy Evaluation :** Delaying the evaluation of an expression until its value is actually needed. This can improve performance and support infinite data structures.

Languages that support functional programming include Haskell, Scala, Clojure, Erlang, and Lisp. However, many mainstream languages, such as JavaScript, Python, and Java, also incorporate functional programming features to varying degrees.

# Lambda Expressions in Java

Lambda expressions were introduced in Java 8 to provide a concise way to express instances of single-method interfaces (also known as functional interfaces). They enable you to treat functionality as a method argument or to create anonymous classes more concisely. Lambda expressions primarily aim to simplify the syntax needed to create anonymous inner classes.

## What are Lambda Expressions?

Lambda expressions, also known simply as lambdas, are anonymous methods (functions) that can be passed around and executed later. They allow you to treat functionality as a method argument or to create anonymous classes more concisely.

## Syntax of Lambda Expressions

The syntax of a lambda expression consists of three parts: 

1. **Parameters**: A lambda expression can have zero or more parameters. The type of each parameter can be explicitly declared or inferred.

2. **Arrow token (->)**: It is used to separate the parameter list from the body of the lambda expression. It is also called the lambda operator.

3. **Body**: It contains the code that defines the functionality of the lambda expression. It can consist of a single expression or a block of code.

Here's the basic syntax:

```java
(parameters) -> expression
```
or

```java
(parameters) -> { statements; }
```
### Examples
### 1. Lambda with No Parameters:
```java
() -> System.out.println("Hello Lambda!");
```
### 2. Lambda with Single Parameter:
```java
(x) -> x * x
```
### 3. Lambda with Multiple Parameters:
```java
(x, y) -> x + y
```
### 4. Lambda with Body:
```java
(x, y) -> {
    int sum = x + y;
    return sum;
}
```
### 5. Lambda as Method Parameter:
```java
List<String> names = Arrays.asList("Alice", "Bob", "Charlie");
names.forEach(name -> System.out.println(name));
```
### Benefits of Lambda Expressions
**Conciseness :** Lambda expressions reduce boilerplate code and make your code more readable by focusing on the actual functionality.

**Improved Code Organization :** By allowing code to be passed around more flexibly, lambdas can promote a more modular and organized code structure.

**Parallelism :** Lambdas facilitate writing code that can be executed in parallel using features like Java's Stream API.

**Enhanced APIs :** Many new APIs introduced in Java 8 and later are designed to work seamlessly with lambdas, providing developers with more powerful and expressive tools.

**Functional Programming Paradigm :** Lambda expressions encourage the use of functional programming paradigms, leading to cleaner, more declarative code.

### Conclusion
Lambda expressions are a powerful addition to the Java language, enabling developers to write more expressive and concise code. By understanding their syntax and benefits, you can leverage lambdas to make your Java code more efficient and maintainable.






