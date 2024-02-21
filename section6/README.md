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
### Example 💡
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
#### Example 💡
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
#### Example 💡
```java
public class LengthMethodDemo {

    public static void main(String[] args) {
        String str1 = "Hello";
        String str2 = "World";
        String combined = str1+ " "+str2;

        int length1 = str1.length();
        int length2 = str2.length();
        int length3 = combined.length();

        int emptyLength = "".length(); 
        int length4 = "Hello".length();

        System.out.println(combined);// Output : 11
        System.out.println(emptyLength);// Output : 0
    }
}
```
### Usage
The length() method is commonly used to find the length of a string in Java. It is particularly useful when you need to validate input length, iterate over characters in a string, or perform other string manipulation tasks.
### Notes ✍️
- The length of a string is equal to the number of Unicode code units in the string.
- This method returns 0 if the string is empty ("").
### Conclusion 🎉
- The length() method in Java's String class is a simple yet powerful tool for determining the length of a string. With its straightforward syntax and predictable behavior, it provides developers with a convenient way to retrieve the number of characters in a string. Whether you're validating user input, iterating through characters, or performing string manipulation tasks, 'length()' is there to help you get the job done efficiently.
- So go ahead, leverage the length() method in your Java projects and let it simplify your string handling tasks! 🚀
## String.equals() Method in Java
The `equals()` method in Java is used to compare the contents of two strings. It returns `true` if the strings are equal, and `false` otherwise.
### Return Value
Return value of the `equals()` method is 'boolean'.
#### Example 💡 
```java
public class StringComparisonDemo {

    public static void main(String[] args) {

        String str1 = new String("Hey");
        String str2 = new String("Hello");
        String str3 = new String("Hey");

        boolean b1 = str1.equals(str2); // false
        boolean b2 = str1.equals(str3); // true

        boolean b3 = str1.equals("Hey"); // true
        boolean b4 = "Hey".equals(str1);// true
        boolean b5 = "Hey".equals("Hello");// false

        String str4 ="java";
        String str5 ="JAVA";
        boolean b6 = str4.equalsIgnoreCase(str5); // true

    }

}
```
### Important Notes ✍️
- The equals() method is case-sensitive.
- It's recommended to use equals() to compare strings rather than == operator, which compares references.
## String.compareTo() Method in Java
The `compareTo()` method in Java is used to compare two strings lexicographically. It returns an integer value that indicates whether the current string is less than, equal to, or greater than the specified string.
#### Return Value
- 0 if the strings are equal.
- A negative integer if the current string is lexicographically less than the specified string.
- A positive integer if the current string is lexicographically greater than the specified string.
#### Example 💡
```java
public class StringComparisonDemo {

    public static void main(String[] args) {

        int comparison1 = "java".compareTo("java"); // 0
        int comparison2 = "java".compareTo("python"); // -6
        int comparison3 = "python".compareTo("java"); // 6

    }

}
```
#### Usage 🚀
The compareTo() method is useful when you need to compare strings alphabetically or numerically in Java.
#### Conclusion 🎉
The compareTo() method in Java is a powerful tool for comparing strings lexicographically. By returning an integer value indicating whether one string is less than, equal to, or greater than another, it facilitates various sorting and comparison tasks in Java programming. Understanding how to use compareTo() effectively can greatly enhance your ability to manipulate and analyze strings in Java applications.
## String.charAt() Method in Java
The `String.charAt()` method in Java returns the character located at the specified index within the given string. The index value should be between 0 and `length() - 1`.
### Parameters
**index :** An integer representing the index of the character.
### Return Value
The method returns the character at the specified index within the string.
### Exceptions
**IndexOutOfBoundsException :** If the index argument is negative or not less than the length of the string.
#### Example 💡
```java
public class CharAtMethodDemo {

    public static void main(String[] args) {
        String java = "JAVA";
        char j = java.charAt(0); // 'J'
        char exception = java.charAt(4);// IndexOutOfBoundsException, because index value (4) is not with in the range of 'String.length()-1'.
    }

}
```
### Usage 🚀
- Use this method when you need to retrieve a specific character from a string by its index.
- It's handy when you want to iterate over each character in a string.
### Note ✍️
- Remember that index starts from 0. So, the first character of the string is at index 0.
### Conclusion 🎉
- The String.charAt() method in Java provides a simple and efficient way to access individual characters within a string by their index. By specifying the desired index, you can retrieve the character located at that position in the string.
- This method is particularly useful when you need to work with individual characters within a string, such as extracting specific characters or iterating through each character in the string.
- However, it's important to be mindful of the index values to avoid IndexOutOfBoundsException. The index should be within the range of 0 to length() - 1 for the string.
- Overall, String.charAt() is a fundamental method for string manipulation in Java, offering versatility and ease of use in various string processing tasks.
- Happy coding! 💻 🙂.
## isEmpty() Method in Java
The `isEmpty()` method in Java is used to check whether a string is empty or not. An empty string is defined as a string that has a length of zero.
### Return Value
- 'true' if the length of the string is 0, indicating that it is empty.
- 'false' otherwise
#### Example
```java
public class EmptyCheckDemo {

    public static void main(String[] args) {
        String myString = "";
        boolean isEmpty = myString.isEmpty(); //true
        boolean isLengthZero = myString.length()==0;// true
        boolean isEqualEmpty = "".equals(myString); //true

        String nullString = null;
        boolean isnullEmpty = "".equals(nullString); //false
        // boolean isEmptyNull = nullString.length()==0; // NullPointerException
    }

}
```
### Usage  🚀
The isEmpty() method is commonly used in scenarios where you need to check if a string contains any meaningful content before performing further operations on it.
### Notes ✍️
- The 'isEmpty()' method is a part of the java.lang.String class and can be called on any string object.
- It's important to handle empty strings appropriately in your code to avoid unexpected behavior, especially when dealing with user input or data processing.
### Conclusion 🎉
- The isEmpty() method in Java provides a convenient way to check whether a string is empty or not. By simply calling this method on a string object, you can quickly determine if it contains any meaningful content or if it's just a blank string.
- This method is particularly useful in scenarios where you need to validate user input, process data, or control flow based on the presence of content in a string. By incorporating isEmpty() into your Java code, you can ensure that your applications handle empty strings gracefully and avoid unexpected behavior.
- Remember to use isEmpty() judiciously in your code, especially when dealing with user input or data processing, to enhance the reliability and robustness of your Java applications.
## toUpperCase() and toLowerCase() methods in Java
Java provides the `toUpperCase()` and `toLowerCase()` methods in the `String` class to convert the case of characters within a string. These methods are commonly used when you need to manipulate or normalize string data, such as converting text to uppercase for comparison or formatting purposes.
## toUpperCase()
The `toUpperCase()` method converts all the characters in a `String` to uppercase. Here's the syntax :
```java
String upperCaseString = originalString.toUpperCase();
```
#### Example
```java
String str = "Hello, World!";
String upperCaseStr = str.toUpperCase();
System.out.println(upperCaseStr); // Output: HELLO, WORLD!
```
## toLowerCase()
The toLowerCase() method converts all the characters in a String to lowercase. Here's the syntax :
```java
String lowerCaseString = originalString.toLowerCase();
```
#### Example
```java
String str = "Hello, World!";
String lowerCaseStr = str.toLowerCase();
System.out.println(lowerCaseStr); // Output: hello, world!
```
### Usage 🚀
These methods are useful for case-insensitive string comparisons, normalizing user input, and formatting string data for output. They are commonly used in various applications, including text processing, data validation, and user interfaces.
### Considerations  🤔
- **Locale :** It's important to note that the behavior of these methods can vary based on the locale settings of the system. In some languages, certain characters may have different uppercase or lowercase representations.
- **Immutability :** Both toUpperCase() and toLowerCase() methods return a new String object with the modified case. The original string remains unchanged.
### Conclusion 🎉
The toUpperCase() and toLowerCase() methods provide convenient ways to convert the case of characters within a string in Java. Understanding their usage and considerations can help you effectively manipulate string data in your Java applications.
## String.valueOf() Method in Java
The String.valueOf() method in Java is a static method provided by the String class, which converts different types of data, including primitive types and objects, into their string representations.
```java
public static String valueOf(Object obj)
```
### Parameters
- obj: The object whose string representation is to be returned.
### Return Value
- Returns the string representation of the specified object. If the specified object is 'null', it returns the string "null".
#### Example























