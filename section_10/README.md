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
#### In this example:
- `Vehicle` is the superclass, and `Car` is the subclass.
- `Car` inherits the `move()` method from Vehicle.
-` Car` also has its own method `accelerate()`.
### Types of Inheritance
**1.Single Inheritance :** A subclass extends only one superclass.
**2.Multilevel Inheritance :** A subclass extends another subclass.
**3.Hierarchical Inheritance :** Multiple subclasses extend the same superclass.
**4.Multiple Inheritance (achieved through interfaces):** A class implements multiple interfaces.
### Rules and Considerations
When working with inheritance in Java, keep these points in mind:
- Java does not support multiple inheritance for classes (i.e., a class cannot extend more than one class). However, it supports multiple inheritance through interfaces.
- The access level of the inherited members depends on their access modifiers. Inherited members with private access are not visible in the subclass.
- Constructors are not inherited but can be invoked using the super() keyword.
- Overriding allows a subclass to provide a specific implementation for a method defined in the superclass.
### When to Use Inheritance
- You want to model an "is-a" relationship between classes (e.g., a Car is-a Vehicle).
- You need to reuse code from existing classes.
- You want to establish a hierarchical structure to organize classes.
### Conclusion
Inheritance is a powerful feature in Java that allows classes to inherit properties and behaviors from other classes. By understanding and leveraging inheritance, you can write more efficient and maintainable code.
## Object Class in Java
## Methods
### public boolean equals(Object obj)
The equals method is used to compare the current object with another object for equality. By default, this method compares the memory addresses of the objects. However, it is often overridden by subclasses to provide custom equality comparison.

### public int hashCode()
The hashCode method returns a hash code value for the object. This method is used in conjunction with hash-based data structures such as HashMap and HashSet.

### public String toString()
The toString method returns a string representation of the object. By default, this method returns a string consisting of the class name followed by the "@" symbol and the object's hash code.

### protected Object clone() throws CloneNotSupportedException
The clone method creates and returns a copy of the object. It is declared protected and must be overridden in subclasses to support cloning.

### public final Class<?> getClass()
The getClass method returns the runtime class of the object. It returns an instance of the Class class that provides information about the class.

### public final void notify()
The notify method wakes up a single thread that is waiting on the object's monitor.

### public final void notifyAll()
The notifyAll method wakes up all threads that are waiting on the object's monitor.

### public final void wait() throws InterruptedException
The wait method causes the current thread to wait until another thread calls the notify() or notifyAll() method on the object.

### public final void wait(long timeout) throws InterruptedException
The wait method causes the current thread to wait until another thread calls the notify() or notifyAll() method on the object, or until the specified timeout expires.

### public final void wait(long timeout, int nanos) throws InterruptedException
Similar to the previous wait method, but allows specifying a timeout in nanoseconds.
#### Example
```java
public class ObjectExample {
    public static void main(String[] args) {
        Object obj1 = new Object();
        Object obj2 = new Object();

        // Using equals method
        if (obj1.equals(obj2)) {
            System.out.println("Objects are equal");
        } else {
            System.out.println("Objects are not equal");
        }

        // Using hashCode method
        System.out.println("Hash code of obj1: " + obj1.hashCode());
        System.out.println("Hash code of obj2: " + obj2.hashCode());

        // Using toString method
        System.out.println("String representation of obj1: " + obj1.toString());

        // Using getClass method
        System.out.println("Class of obj1: " + obj1.getClass().getName());
    }
}
```
### Notes
- The `Object` class provides default implementations for many of its methods, which can be overridden by subclasses to customize behavior.
- When overriding the `equals` method, it is recommended to also override the `hashCode` method to maintain the general contract between the two methods.
- The `wait`, `notify`, and `notifyAll` methods are used for inter-thread communication and synchronization.
## is-a Realationship
In Java, the "is-a" relationship is a fundamental principle of object-oriented programming (OOP) that is implemented through inheritance. It signifies a relationship between classes where one class is considered to be a specialized version of another class.
#### Example
```java
// Superclass
class Animal {
    void makeSound() {
        System.out.println("Animal makes a sound.");
    }
}

// Subclass
class Dog extends Animal { // Dog is a Animal
    void wagTail() {
        System.out.println("Dog wags its tail.");
    }
}

// Subclass
class Cat extends Animal { // Cat is a Animal
    void purr() {
        System.out.println("Cat purrs.");
    }
}
```
## "has-a" Relationship 
In the "has-a" relationship, one class (usually referred to as the container or composite class) contains an instance of another class (referred to as the contained or component class) as one of its members. This implies that the container class "has" an object of the component class.
#### Example
```java
public class Car {
    private Engine engine;

    public Car(Engine engine) {
        this.engine = engine;
    }

    // Other methods and attributes of the Car class...
}

public class Engine {
    // Properties and methods of the Engine class...
}
```
### In this example:
The `Car` class has an instance of the Engine class as one of its attributes.
The `Engine` class represents the component that the Car class possesses.
### Benefits of "has-a" Relationship:
**1.Modularity :**
- Allows for modular design by encapsulating related functionality within separate classes.
#### 2.Code Reusability :
- Promotes code reusability as the same component class can be used across multiple container classes.
#### 3.Flexibility :
- Provides flexibility in designing complex systems by composing smaller, reusable components.
### How to Use:
When designing classes in Java, consider whether one class needs to contain an instance of another class to represent a "has-a" relationship. If so, define the appropriate attributes and methods to interact with the contained class.

### Conclusion:
Understanding the "has-a" relationship is crucial for designing modular and maintainable Java applications. By utilizing this relationship effectively, you can create flexible and reusable code that accurately models real-world scenarios.
## Up-casting
Up-casting refers to the process of converting an object of a subclass to a reference of its superclass. It is implicit and does not require any explicit casting operator. Up-casting is always safe because a subclass object inherently possesses all the attributes and behaviors of its superclass.
#### Example:
```java
class Animal {
    public void sound() {
        System.out.println("Animal makes a sound"); //   
    }
}

class Dog extends Animal {
    @Override
    public void sound() {
        System.out.println("Dog barks");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal animal = new Dog(); // Up-casting
        animal.sound(); // Output: Dog barks
    }
}
```
### Down-casting
Down-casting is the opposite of up-casting. It refers to the process of converting a reference of a superclass type to its subclass type. Down-casting is explicit and requires the use of the casting operator. It can potentially lead to a `ClassCastException` at runtime if the object being casted is not actually an instance of the target subclass.
#### Example:
```java
class Animal {
    public void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    @Override
    public void sound() {
        System.out.println("Dog barks");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal animal = new Dog(); // Up-casting
        animal.sound(); // Output: Dog barks
    }
}
public class Main {
    public static void main(String[] args) {
        Animal animal = new Dog(); // Up-casting
        Dog dog = (Dog) animal; // Down-casting
        dog.sound(); // Output: Dog barks
    }
}
```
In the above example, we first up-cast a Dog object to an Animal reference. Then, we down-cast the Animal reference back to a Dog reference. Since the original object was indeed a Dog, down-casting is safe in this scenario.
### Conclusion
Up-casting and down-casting are important concepts in Java that allow for flexibility and polymorphism in object-oriented programming. While up-casting is implicit and safe, down-casting requires explicit type casting and should be used carefully to avoid runtime errors.
### instanceof Operator
The `instanceof` operator in Java is used to test whether an object is an instance of a particular class or interface. It returns either `true` or `false` based on whether the object is an instance of the specified type.
#### Example
```java
public class Main {
    public static void main(String[] args) {
        String str = "Hello";

        // Using instanceof to check if str is an instance of String class
        boolean isString = str instanceof String;
        System.out.println("Is str an instance of String? " + isString); // Output: true

        // Using instanceof to check if str is an instance of Object class
        boolean isObject = str instanceof Object;
        System.out.println("Is str an instance of Object? " + isObject); // Output: true // Object class is super class of all the classes


        // Using instanceof to check if str is an instance of Integer class
        boolean isInteger = str instanceof Integer;
        System.out.println("Is str an instance of Integer? " + isInteger); // Output: false
    }
}
```
In this example:
- We create a String object str.
- We use the instanceof operator to check if str is an instance of the `String` class, which returns `true`.
- Similarly, we check if `str` is an instance of the `Object` class, which also returns `true`.
- Finally, we check if str is an instance of the `Integer` class, which returns `false`.
### Key Points
- The `instanceof` operator is used for type checking at runtime.
- It returns true if the object is an instance of the specified type or any of its subtypes, otherwise false.
- It's commonly used when working with polymorphic code to determine the actual type of an object before performing certain operations.
## Static Binding and Dynamic Binding
In Java, binding refers to the process of associating a method call with the method body. There are two types of binding in Java: static binding and dynamic binding.
## Static Binding
Static binding, also known as early binding, occurs during compile time. In static binding, the method call is resolved by the compiler based on the reference type. This means that the compiler determines which method to call based on the reference type of the object at compile time.
### Dynamic Binding
Dynamic binding, also known as late binding, occurs during runtime. In dynamic binding, the method call is resolved by the JVM (Java Virtual Machine) based on the actual object type. This means that the JVM determines which method to call based on the actual object type at runtime.
#### Example:
```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    void sound() {
        System.out.println("Dog barks");
    }
}

class Cat extends Animal {
    void sound() {
        System.out.println("Cat meows");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal animal1 = new Animal();
        Animal animal2 = new Dog();
        Animal animal3 = new Cat();

        animal1.sound(); // Output: Animal makes a sound (static binding)
        animal2.sound(); // Output: Dog barks (dynamic binding)
        animal3.sound(); // Output: Cat meows (dynamic binding)
    }
}

```
In this example:

- animal1 is of type Animal, and the sound() method call is resolved at compile time because the reference type is known.
- animal2 is of type Animal, but it refers to a Dog object. The method call is resolved at runtime, and the sound() method of Dog class is invoked (dynamic binding).
- animal3 is also of type Animal, but it refers to a Cat object. Again, the method call is resolved at runtime, and the sound() method of Cat class is invoked (dynamic binding).
- This demonstrates the difference between static binding, where the method is determined at compile time based on the reference type, and dynamic binding, where the method is determined at runtime based on the actual object type.










