# Generics in Java 📚
Generics in Java are a powerful feature that allow you to write code that can work with different types while providing compile-time type safety. They were introduced in Java 5 to enable developers to create classes, interfaces, and methods that operate on a wide range of data types without sacrificing type safety.
## Why we need Generics in java
Generics in Java serve several important purposes:

**Type Safety :** Generics provide compile-time type checking, which helps catch type-related errors at compile time rather than runtime. This ensures that you cannot insert the wrong type of object into a generic container, reducing the likelihood of bugs and making code more robust.

**Code Reusability :** Generics enable you to write code that can operate on a wide range of data types without sacrificing type safety. This promotes code reuse, as you can write generic classes, interfaces, and methods that work with different types of data.

**Abstraction :** Generics allow you to write code that is more abstract and flexible, as it can work with different types of data. This promotes cleaner, more modular code that is easier to maintain and extend.

**Performance :** Generics can improve performance by eliminating the need for type casting in many situations. This can lead to more efficient code execution, especially in performance-critical applications.

**API Design :** Generics enable you to design APIs that are more flexible and easier to use. By using generics, you can create APIs that are type-safe and provide better compile-time checking, leading to improved usability and readability.

Overall, generics in Java are essential for writing robust, reusable, and type-safe code, and they play a crucial role in modern Java programming. They help improve code quality, maintainability, and performance, making them an indispensable feature of the language.
## Generic Class
GenericClass.java
```java
public class GenericClass<T> {
    private T data;

    public GenericClass(T data) {
        this.data = data;
    }

    public T getData() {
        return data;
    }

    public void setData(T data) {
        this.data = data;
    }

    public void printType() {
        System.out.println("Type of data: " + data.getClass().getName());
    }
}
```
### GenericClass<T> in Java

This is a simple Java class `GenericClass<T>` that demonstrates the use of generics in Java programming.

The `GenericClass<T>` is a generic class, where `T` is a type parameter. This allows the class to be flexible in handling different data types without the need for explicit casting.

## Usage

1. **Instantiate GenericClass with a specific data type:**

    ```java
    // Instantiate GenericClass with String data
    GenericClass<String> stringGenericClass = new GenericClass<>("Hello, world!");
    ```

2. **Set and Get Data:**

    ```java
    // Set new data
    stringGenericClass.setData("New data");

    // Get data
    String data = stringGenericClass.getData();
    ```

3. **Print Type:**

    ```java
    // Print the type of data
    stringGenericClass.printType();
    ```

### Example

```java
public class Main {
    public static void main(String[] args) {
        // Instantiate GenericClass with String data
        GenericClass<String> stringGenericClass = new GenericClass<>("Hello, world!");

        // Set new data
        stringGenericClass.setData("New data");

        // Get data
        String data = stringGenericClass.getData();
        System.out.println("Data: " + data);

        // Print the type of data
        stringGenericClass.printType();
    }
}
```
## Generic Methods
Generic methods are methods that introduce their own type parameters. This allows you to create methods that operate on parameterized types. They are essential in writing reusable and type-safe code in Java. This README provides an overview of generic methods in Java and how to use them effectively.
### Why Use Generic Methods?
- **Reusability**: Generic methods allow you to write methods that can work with any type, enhancing code reusability.
- **Type Safety**: With generic methods, you can catch type mismatches at compile time, reducing runtime errors.
- **Cleaner Code**: By using generics, you can write cleaner and more concise code, avoiding the need for casting.
### Syntax

A generic method declaration looks like a regular method declaration, except that it includes a type parameter section delimited by angle brackets (< and >) before the method's return type.

```java
public <T> void methodName(T parameter) {
    // Method implementation
}
```


