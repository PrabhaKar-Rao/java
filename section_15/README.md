# Method in Object Class
In Java, an ` Object` class refers to any class that extends the fundamental base class, Object. Every class in Java implicitly or explicitly extends Object, which is the root of the class hierarchy.
## Object.getClass()
The `getClass()` method in Java is a part of the Object class, which is the root of the Java class hierarchy. It returns the runtime class of an object. In other words, it returns an instance of the Class class representing the runtime class of the object.
### Syntax
```java
public final Class<?> getClass()
```
### Return Value
- Returns the runtime class of this object.
#### Example
```java
package com.eazybytes.object.demo;

public class GetClassDemo {

    public static void main(String[] args) {
        Person person = new Person();
        Class prsnClass = person.getClass();
        System.out.println(prsnClass.getName());
        System.out.println(prsnClass.getSimpleName());
        System.out.println(prsnClass.getPackageName());
    }

}
```
### Usage
- Use `getClass()` when you need to determine the runtime class of an object at runtime.
- It's commonly used in scenarios where the exact type of an object needs to be identified dynamically.
### Notes
- The `getClass()` method is a final method and cannot be overridden.
- If the object is null, a `NullPointerException` will be thrown when getClass() is invoked on it.
### The getClass() method is a final method and cannot be overridden.
If the object is null, a NullPointerException will be thrown when getClass() is invoked on it.
## Object.hashCode()
In Java, `Object.hashCode()` is a method provided by the `Object` class, which is the root of the class hierarchy. This method returns a hash code value for the object. It is crucial for various algorithms, such as hashing-based collections like `HashMap` and `HashSet`.
### Syntax
```java
public int hashCode()
```
### Description
- Returns a hash code value for the object. This value is typically used to support hash-based collections.
- The general contract of hashCode method is:
  - Whenever it is invoked on the same object more than once during an execution of a Java application, the hashCode method must consistently return the same 
  - integer, provided no information used in equals comparisons on the object is modified.
  - If two objects are equal according to the equals(Object) method, then calling the hashCode method on each of the two objects must produce the same integer result.
  - It's not required that if two objects are unequal according to the equals(Object) method, then calling the hashCode method on each of the two objects must 
  - produce distinct integer results. However, the programmer should be aware that producing distinct integer results for unequal objects may improve the performance of hash tables.
#### Example
```java
public class MyClass {
    private String name;
    private int id;

    public MyClass(String name, int id) {
        this.name = name;
        this.id = id;
    }

    @Override
    public int hashCode() {
        int result = 17;
        result = 31 * result + name.hashCode();
        result = 31 * result + id;
        return result;
    }

    // other methods...
}
```
In this example, the `hashCode` method is overridden to generate a hash code based on the name and `id` fields of the object.
### Best Practices
- Consistency with `equals()` : If you override the `equals()` method, make sure to also override the `hashCode()` method and ensure that they are consistent with each other.
- Efficiency: While it's not strictly required that hash codes be unique, producing distinct hash codes for distinct objects can improve the performance of hash-based collections.
- Stable Hash Codes: Ensure that the hash code of an object remains the same over its lifetime, as long as the information used in `equals()` comparisons remains constant.
- Use in Collections: Be mindful when using objects with mutable state as keys in hash-based collections, as changing the state of the object after it has been used as a key can lead to unexpected behavior.
## Object.equals()
`Object.equals()` is a method in Java that is used to compare the equality of two objects. It is inherited by all classes in Java since all classes ultimately extend the `Object` class.
### Syntax
```java
public boolean equals(Object obj)
```
### Parameters
- `obj` : The object to be compared for equality with this object.
### Return Value
- `true` if the specified object is equal to this object.
- `false` otherwise.
### Usage
The `equals()` method is typically overridden in classes that need custom equality comparison. By default, it compares object references, i.e., whether the two object references point to the same memory location.
```java
public class MyClass {
    private int value;

    // Constructor, getters, setters...

    @Override
    public boolean equals(Object obj) {
        if (this == obj)
            return true;
        if (obj == null || getClass() != obj.getClass())
            return false;
        MyClass myObj = (MyClass) obj;
        return value == myObj.value;
    }

    // Other methods...
}
```
In the above example, the `equals()` method is overridden to compare the `value` attribute of two `MyClass` objects for equality.
### Best Practices
- Override `equals()` when necessary : If your class needs a custom equality comparison, override the `equals()` method to provide it.
- Follow the contract: Ensure that your implementation of `equals()` satisfies the contract defined in the Java documentation.
- Override hashCode(): If you override `equals()`, it's recommended to also override the `hashCode()` method to maintain consistency.
```java
public class Main {
    public static void main(String[] args) {
        MyClass obj1 = new MyClass(10);
        MyClass obj2 = new MyClass(10);

        System.out.println(obj1.equals(obj2));  // Output: true
    }
}
```
## Object.toString()
The `toString()` method in Java is a method provided by the `Object` class, which is the root of the Java class hierarchy. It returns a string representation of the object. The default implementation provided by the `Object` class returns a string consisting of the class name followed by the "@" character and the object's hashcode in hexadecimal format.
### Syntax
```java
public String toString()
```
### Return Value
- A string representation of the object.
#### Example
```java
public class MyClass {
    private int id;
    private String name;

    public MyClass(int id, String name) {
        this.id = id;
        this.name = name;
    }

    @Override
    public String toString() {
        return "MyClass{" +
                "id=" + id +
                ", name='" + name + '\'' +
                '}';
    }

    public static void main(String[] args) {
        MyClass obj = new MyClass(1, "Example");
        System.out.println(obj.toString());
    }
}
```
```java
MyClass{id=1, name='Example'}
```
### Usage
- Override the `toString()` method in your custom classes to provide a meaningful string representation of the object.
- Useful for debugging purposes to print object information.
- Used in logging or displaying object information to users.
### Note 
If you don't override `toString()` in your custom class, you'll get the default implementation provided by the `Object` class, which may not provide meaningful information about the object.









