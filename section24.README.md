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

## How to Build Lambda Expressions in Java
Lambda expressions in Java are a powerful feature introduced in Java 8, allowing you to treat functionality as a method argument, or to create anonymous functions. This README provides a guide on how to build lambda expressions in Java.

## What are Lambda Expressions?
Lambda expressions introduce the concept of functional programming to Java. They allow you to treat functionality as a method argument, or to create anonymous functions. Lambda expressions are particularly useful when working with collections and streams, where you need to pass behavior as a parameter.

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
### Examples 💡
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

### Conclusion 🎉
Lambda expressions are a powerful addition to the Java language, enabling developers to write more expressive and concise code. By understanding their syntax and benefits, you can leverage lambdas to make your Java code more efficient and maintainable.

## Functional Interface
Functional Interface in Java is an interface that contains only one abstract method. It can have any number of default or static methods but must contain exactly one abstract method. They are also known as Single Abstract Method (SAM) interfaces.

Functional Interfaces play a crucial role in enabling functional programming features in Java, particularly with the introduction of lambda expressions in Java 8.

## Usage

To define a functional interface in Java, you can use the `@FunctionalInterface` annotation. This annotation is not mandatory, but it's recommended as it ensures the interface has only one abstract method.

```java
@FunctionalInterface
interface MyFunctionalInterface {
    void myMethod();
}
```
Now, you can use this functional interface to create lambda expressions or method references


```java
public class Main {
    public static void main(String[] args) {
        // Using lambda expression
        MyFunctionalInterface myLambda = () -> System.out.println("Hello from lambda");
        myLambda.myMethod();

        // Using method reference
        MyFunctionalInterface myMethodRef = Main::someMethod;
        myMethodRef.myMethod();
    }

    static void someMethod() {
        System.out.println("Hello from method reference");
    }
}
```

### Characteristics
Single Abstract Method (SAM): Functional interfaces must contain exactly one abstract method.
@FunctionalInterface Annotation: While not mandatory, using this annotation helps to ensure that the interface is intended to be used as a functional interface.
Lambda Expressions: Functional interfaces are often used with lambda expressions to provide concise implementations of the abstract method.
Method References: Method references allow you to refer to methods or constructors without invoking them.
### Examples
Here are some common examples of functional interfaces in Java:

- **Runnable :** Represents a task that can be executed.
- **Callable :** Represents a task that returns a result and may throw an exception.
- **Comparator :** Used to compare two objects.
- **Supplier :** Provides a value without taking any input.
- **Consumer :** Consumes a value without returning any result.
- **Function :** Represents a function that accepts one argument and produces a result.
### Benefits
- **Concise Code :** Functional interfaces combined with lambda expressions allow for more concise and expressive code.
- **Readability :** Lambda expressions can make the code more readable by focusing on what needs to be done rather than how it is done.
- **Flexibility :** Functional interfaces provide flexibility in designing APIs, allowing methods to accept behaviors as parameters.
### Conclusion
Functional interfaces in Java enable functional programming paradigms by allowing the use of lambda expressions and method references. They provide a concise and expressive way to define behaviors, leading to cleaner and more maintainable code.

## Functional Interface and Lambda Expressions
Functional Interface and Lambda Expressions are two closely related concepts in Java, introduced in Java 8. They are instrumental in enabling functional programming paradigms within the language.
### Functional Interface
A Functional Interface in Java is an interface that contains exactly one abstract method. It may contain any number of default or static methods, but it must have exactly one abstract method. Functional interfaces are also known as Single Abstract Method (SAM) interfaces.

Functional interfaces serve as the foundation for lambda expressions in Java. They provide a way to define the signature for lambda expressions.

### Lambda Expressions

Lambda Expressions, introduced in Java 8, provide a concise syntax for representing anonymous functions. They allow you to express instances of single-method interfaces (functional interfaces) more compactly.

Lambda expressions are essentially a way to pass functionality as an argument to a method. They provide a clear and concise way to represent behavior without the need for verbose anonymous inner classes.

Linking Functional Interfaces and Lambda Expressions

Lambda expressions are intimately linked with functional interfaces in Java. When you use a lambda expression, you are essentially implementing the abstract method of a functional interface in a more concise and expressive way.

Let's take a look at an example:

```java
// Functional Interface
@FunctionalInterface
interface MyFunctionalInterface {
    void myMethod();
}

public class Main {
    public static void main(String[] args) {
        // Lambda Expression
        MyFunctionalInterface myLambda = () -> System.out.println("Hello from lambda");
        myLambda.myMethod();
    }
}
```
In the example above:

We define a functional interface MyFunctionalInterface with a single abstract method myMethod().
We then create a lambda expression () -> System.out.println("Hello from lambda"), which represents an instance of MyFunctionalInterface.
Finally, we invoke the myMethod() using the lambda expression.
This demonstrates how lambda expressions can be used to implement the abstract method of a functional interface concisely.

### Benefits
The linking of functional interfaces and lambda expressions in Java provides several benefits:

**Concise Syntax :** Lambda expressions allow for more concise and readable code compared to anonymous inner classes.
**Functional Programming :** Enables functional programming paradigms in Java by providing a way to pass behavior as an argument to methods.
**Improved Expressiveness :** Enhances code expressiveness by focusing on what needs to be done rather than how it is done.
**Flexibility :** Provides flexibility in designing APIs by allowing methods to accept behaviors as parameters.
### Conclusion
Functional interfaces and lambda expressions in Java are closely linked concepts that enable functional programming paradigms within the language. By using lambda expressions, you can implement the abstract methods of functional interfaces concisely and expressively, leading to cleaner and more maintainable code.








