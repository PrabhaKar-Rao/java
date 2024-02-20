# Strings in Java
Strings are one of the most commonly used data types in Java, representing a sequence of characters. In Java, strings are immutable, meaning their values cannot be changed after they are created.
## Creating Strings
### Using String Literal
```java
String str="Hello, World! 😀";
```
###  Using the new Keyword
```java
String str=new String("Hello, World! 😀";
```
### Using 'StringBuilder' or 'StringBuffer'
```java
StringBuilder stringBuilder = new StringBuilder();
stringBuilder.append("Hello");
stringBuilder.append(", ");
stringBuilder.append("World! 😀 ");
String str = stringBuilder.toString();
```
### String Pool
```java
public class StringPool {

    public static void main(String[] args) {
        String str1 = "Hello";
        String str2="Hello";
        String str3="hai";
        Sytsem.out.println(str1==str2);// true, because content of 'str1' and 'str2' is same thats why both referring to the same memory loaction.

        Sytsem.out.println(str1.hashCode());// eg. 151516
        Sytsem.out.println(str2.hashCode()); // eg. 151516 // both 'HashCode' values are same because content of the both strings are same.


        String obj1=new String("hello");
        String obj2=new String("hello");
        String Obj3=new String("hai");

        Sytsem.out.println(obj1.hashCode());//eg. 121212
        Sytsem.out.println(obj2.hashCode());//eg. 121212
        Sytsem.out.println(obj3.hashCode());//eg. 124566

        Sytsem.out.println(obj1==obj2);// false, even if HashCode values are same both objects are not stored same memory loaction.
        
    }

}
```
## String.intern()
The `intern()` method in the `String` class is a useful tool for managing memory efficiently when working with strings in Java. It returns a canonical representation of the string object, which means that for any two strings `s` and `t`, `s.intern() == t.intern()` holds true if and only if `s.equals(t)`.
### Example
```java
public class Main {
    public static void main(String[] args) {
        String s1 = "hello";
        String s2 = new String("hello");
        
        String internedS1 = s1.intern();
        String internedS2 = s2.intern();
        
        // Prints: true
        System.out.println(internedS1 == internedS2);
    }
}
```
