# Inheritance in Java
Inheritance is a fundamental concept in object-oriented programming (OOP) languages like Java. It allows a class (subclass/derived class) to inherit properties and behaviors from another class (superclass/base class). This promotes code reusability and establishes a hierarchical relationship between classes.
```java
# Inheritance in Java

Inheritance is a fundamental concept in object-oriented programming (OOP) languages like Java. It allows a class (subclass/derived class) to inherit properties and behaviors from another class (superclass/base class). This promotes code reusability and establishes a hierarchical relationship between classes.

## How Inheritance Works

In Java, inheritance is achieved using the `extends` keyword. Here's a simple example:

```java
// Superclass
class Vehicle {
    void move() {
        System.out.println("Vehicle is moving...");
    }
}

// Subclass inheriting from Vehicle
class Car extends Vehicle {
    void accelerate() {
        System.out.println("Car is accelerating...");
    }
}

// Main class
public class Main {
    public static void main(String[] args) {
        Car myCar = new Car();
        myCar.move(); // Output: Vehicle is moving...
        myCar.accelerate(); // Output: Car is accelerating...
    }
}
```
### In this example:
- `Vehicle` is the superclass, and Car is the subclass.
- `Car` inherits the `move()` method from Vehicle.
-` Car` also has its own method `accelerate()`.
## Types of Inheritance
**1.Single Inheritance :** A subclass extends only one superclass.
**2.Multilevel Inheritance :** A subclass extends another subclass.
**3.Hierarchical Inheritance :** Multiple subclasses extend the same superclass.
**4.Multiple Inheritance (achieved through interfaces):** A class implements multiple interfaces.
## Rules and Considerations
When working with inheritance in Java, keep these points in mind:
- Java does not support multiple inheritance for classes (i.e., a class cannot extend more than one class). However, it supports multiple inheritance through interfaces.
- The access level of the inherited members depends on their access modifiers. Inherited members with private access are not visible in the subclass.
- Constructors are not inherited but can be invoked using the super() keyword.
- Overriding allows a subclass to provide a specific implementation for a method defined in the superclass.
## When to Use Inheritance
- You want to model an "is-a" relationship between classes (e.g., a Car is-a Vehicle).
- You need to reuse code from existing classes.
- You want to establish a hierarchical structure to organize classes.


