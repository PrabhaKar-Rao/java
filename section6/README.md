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
## String.intern() Method in Java
The `intern()` method in the `String` class is a useful tool for managing memory efficiently when working with strings in Java. It returns a canonical representation of the string object, which means that for any two strings `s` and `t`, `s.intern() == t.intern()` holds true if and only if `s.equals(t)`.
### Example
```java
public class InternMethodDemo {

    public static void main(String[] args) {
        String hello = "Hello";
        String obj = new String("Hello").intern();
        System.out.println(hello==obj); // false

        String s1 = "hello";
        String s2 = new String("hello");
        System.out.println(s1==s2);
        String s3 = s2.intern();
        System.out.println(s1==s3); //true
    }

}
```
## String.concat() Method in Java
The `concat()` method in Java is used to concatenate one string to the end of another string. It returns a new string that represents the concatenation of the two strings.
```java
public class Concat {
    public static void main(String[] args) {
        String str1 = "Hello";
        String str2 = " World!";
        
        String result = str1.concat(str2);
        System.out.println(result); // Output: Hello World!
    }
}
```
## Escape Sequence Characters and Unicode Character Values in Strings
- In programming, especially when working with strings, it's essential to understand escape sequence characters and Unicode character values. These elements allow developers to represent special characters or control sequences within a string.
- This repository provides a comprehensive reference guide for escape sequence characters and Unicode character values, along with examples demonstrating their usage in various programming languages.
###  Escape Sequence Characters
Escape sequence characters are special characters that are preceded by a backslash (\) in a string. They represent characters that are difficult or impossible to represent directly in code. Common escape sequence characters include :
- `\n` - Newline
- `\t` - Tab
- `\r` - Carriage return
- `\\` - Backslash
- `\"` - Double quote
- `\'` - Single quote
- `\b` - Backspace
- `\f` - Form feed
- `\v` - Vertical tab
- `\xhh` - ASCII character represented by hexadecimal value `hh`
- `\uhhhh` - Unicode character represented by hexadecimal value `hhhh`
- `\Uhhhhhhhh` - Unicode character represented by hexadecimal value `hhhhhhhh`
### Unicode Character Values
Unicode character values represent characters from various writing systems and symbol sets. These values are commonly used to include special characters or symbols in strings. Examples include :
- `\uXXXX` - Unicode character represented by hexadecimal value `XXXX`
- `\UXXXXXXXX` - Unicode character represented by hexadecimal value `XXXXXXXX`
#### Example 
```java
public class EscapeSeqDemo {

    public static void main(String[] args) {
        String name = "\"Madan\"";
        System.out.println(name);// Output : "Madan"

        String m =  "\u004D";
        System.out.println(m);// Output : M
        String unicodeName = "\u004Dadan\u0021";
        System.out.println(unicodeName);// Output : Madan!
    }

}
```
## String.length() Method in Java
The `length()` method in Java is a part of the `String` class. It returns the length of the string - the number of characters in the string.
### Parameters
This method does not take any parameters
### Return Value
The length() method returns an integer value representing the number of characters in the string.
#### Example






