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


# Declaring Methods in Java Class
In Java, methods are functions defined within a class. They encapsulate behavior and define what objects of that class can do. Methods are used to perform specific tasks and manipulate the state of objects.
## Declaring Methods
```java
public class ClassName {
    // Method declaration
    public returnType methodName() {
        // Method body
        // Perform tasks here
        return value; // Return statement (if returnType is not void)
    }
}
```
#### Example
```java
public class Car {

    String model;
    String color;
    int horsePower;

    public void startCar() {
        System.out.println("Vehicle started...");
    }

    public String stopCar() {
        String output = "Vehicle stopped...";
        return output;
    }

}
```
## Method With Parameters
```java
public class ClassName {
    // Method declaration
    public returnType methodName(parameterType parameter1, parameterType parameter2, ...) {
        // Method body
        // Perform tasks here
        return value; // Return statement (if returnType is not void)
    }
}
```
### Example
```java
public class AithmeticOperations {

    public int add(int num1, int num2) {
        int sum =num1+num2;
        return sum;
    }
}
```
##### In the above example :
- 'add' is a method of the 'AithmeticOperations' class.
- It takes two parameters (num1 and num2) of type int.
- It returns the sum of num1 and num2 as an int.

## Method Invocation

If method is static and present in the same class then call that method with method name.
```java
public class AithmeticOperations {
    public static void main(String[]args){
        int result=add(10, 20); // Method Invocation
    }
    public int add(int num1, int num2) {
        return num1 + num2; 
    }
}
```
If method is static and present outside of the class then call that with ClassName.methodName.
```java
public class AithmeticOperations {
    public static void main(String[]args){
        int result=Addition.add(10, 20); // Method Invocation
        System.out.println(result);
    }
}

public class Addition{
      public int add(int num1, int num2) {
        return num1 + num2; 
    }
}
```
## Object Creation
Once you have defined the class, you can create an object of that class using 'new' keyword.
If the method is Non-Static and present inside the same calss then call that method with ObjectReferenceVariable.methodName
```java
public class AithmeticOperations {
    public static void main(String[]args){
        // Create Object of class where the method is present.
        AithmeticOperations aithmeticOperations=new AithmeticOperations(); //Object Creation
        // aithmeticOperations is Object reference variable
        int result=aithmeticOperations.add(10, 20); // Method Invocation
         System.out.println(result);
    }
    public int add(int num1, int num2) {
        return num1 + num2; 
    }
}
```
If the method is Non-Static and present outside calss then call that method with ObjectReferenceVariable.methodName
```java
public class AithmeticOperations {
    public static void main(String[]args){
        // Create Object of class where the method is present.
        Addition addition=new Addition(); //Object Creation
        // addition is Object reference variable
        int result=addition.add(10, 20); // Method Invocation
         System.out.println(result);
    }
}

public class Addition{
      public int add(int num1, int num2) {
        return num1 + num2; 
    }
}

















   
     
     
  
 