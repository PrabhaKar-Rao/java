# Exploring Core Java Concepts
## Declaring Feilds in Java Class
In Java, fields are declared within a class. They represent the state or attributes of objects created from that class. Fields can store data that characterize the objects and are accessible throughout the class.
Fields are declared within the body of a class. Here's the syntax for declaring fields :

   ```java
   public class ClassName {
    // Instance variables (fields)
    dataType fieldName1;
    dataType fieldName2;
    // ...
   }
   ```
### Example
   ```java
   public class Person {
    // Instance variables (fields)
    String name;
    int age;
    double height;
   }
   ```
#### In the above exapmle
- "name", "age", and "height" are fields of the 'Person' class.
- Each field has a data type (String, int, double) followed by the field name.
- These fields represent the characteristics of a 'Person' object.
### Field Types
#### Instance Variables or Non-Static Variables :
Instance variables are associated with objects of the class. Each instance (object) of the class has its own copy of instance variables.
```java
public class MyClass {
    public int instanceVariable; // Instance variable
}
```
#### Static Variables :
Static variables are shared among all instances of a class. They are associated with the class rather than with any object.
```java
public class MyClass {
    public static int staticVariable; // Static variable
}
```
### Access Modifiers
Java provides access modifiers to control the visibility of fields. The commonly used access modifiers are :
- **public :** The field is accessible from any other class.
- **private :** The field is accessible only within the same class.
- **protected :** The field is accessible within the same package and subclasses.
- **default (no modifier) :** The field is accessible only within the same package.
### Example
```java
public class MyClass {
    public int publicField;
    private int privateField;
    protected int protectedField;
    int defaultField; // Default access modifier
}
```
### Conclusion
Declaring fields in a Java class is a fundamental aspect of object-oriented programming. Fields represent the state of objects and store data that characterize them. Understanding how to declare and use fields is crucial for building Java applications.







   
     
     
  
 
