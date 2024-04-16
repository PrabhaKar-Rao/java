# Streams
## Introduction to java.util.stream API in Java
The `java.util.stream` package in Java provides a powerful way to process collections of objects in a functional style. It was introduced in Java 8 as part of the Java Collections Framework.
### What is a Stream?
A Stream in Java represents a sequence of elements and supports different operations to perform computations on these elements. Streams allow for functional-style operations to be performed on collections of objects, such as filtering, mapping, reducing, and more.
### Features
- **Lazy Evaluation:** Streams perform operations only when necessary. Intermediate operations are typically lazy, meaning they do not compute a result until the result is needed by a terminal operation.
- **Parallel Processing:** Streams can leverage parallel processing, making it easier to write parallelizable code to take advantage of multi-core processors.
- **Functional Composition:** Streams provide methods for composing operations in a functional style, making it easy to chain multiple operations together.

### Basic Operations
- **Filtering:** Allows filtering elements based on certain criteria.
- **Mapping:** Allows transforming elements into another form.
- **Reducing:** Performs a reduction on the elements of the stream.
- **Sorting:** Sorts the elements of the stream based on a comparator.

### Example
```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class Main {
    public static void main(String[] args) {
        List<String> names = Arrays.asList("John", "Alice", "Bob", "Charlie", "David");

        // Filter names starting with 'A' and collect them into a new list
        List<String> filteredNames = names.stream()
                                         .filter(name -> name.startsWith("A"))
                                         .collect(Collectors.toList());

        System.out.println(filteredNames); // Output: [Alice]
    }
}
```

## Creating Stream from Collections
Streams provide a modern, functional approach to processing collections of objects in Java, allowing for concise and expressive code.

### Creating a Stream from List

You can easily create a Stream from a List using the `stream()` method introduced in Java 8.

```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Stream;

public class Main {
    public static void main(String[] args) {
        List<String> myList = Arrays.asList("apple", "banana", "orange");
        Stream<String> stream = myList.stream();

        // Use the stream
        stream.forEach(System.out::println);
    }
}
```
### Creating a Stream from Set
Similarly, you can create a Stream from a Set using the stream() method.

```java
import java.util.HashSet;
import java.util.Set;
import java.util.stream.Stream;

public class Main {
    public static void main(String[] args) {
        Set<String> mySet = new HashSet<>();
        mySet.add("apple");
        mySet.add("banana");
        mySet.add("orange");

        Stream<String> stream = mySet.stream();

        // Use the stream
        stream.forEach(System.out::println);
    }
}
```
### Creating a Stream from Map
To create a Stream from a Map, you can use the keySet().stream() or values().stream() methods.

```java
import java.util.HashMap;
import java.util.Map;
import java.util.stream.Stream;

public class Main {
    public static void main(String[] args) {
        Map<Integer, String> myMap = new HashMap<>();
        myMap.put(1, "apple");
        myMap.put(2, "banana");
        myMap.put(3, "orange");

        Stream<Integer> keysStream = myMap.keySet().stream();
        Stream<String> valuesStream = myMap.values().stream();

        // Use the streams
        keysStream.forEach(System.out::println);
        valuesStream.forEach(System.out::println);
    }
}
```
### Conclusion
Creating Streams from collections in Java is straightforward and allows for concise and expressive code. Streams provide powerful features for processing data in a functional style.
