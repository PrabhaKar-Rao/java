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

## Streams have no Storage
Streams in Java are not data storage containers; instead, they provide a way to process elements from a source (such as a collection, array, or I/O channel) in a functional and declarative style. Streams operate on data elements in a sequence and allow for various operations to be performed on those elements, such as filtering, mapping, sorting, and reducing.

### Example
Consider the following example that demonstrates the use of streams to process a list of integers:

```java
import java.util.Arrays;
import java.util.List;

public class Main {
    public static void main(String[] args) {
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);

        // Example 1: Filtering even numbers
        numbers.stream()
               .filter(num -> num % 2 == 0)
               .forEach(System.out::println);

        // Example 2: Mapping numbers to their squares
        numbers.stream()
               .map(num -> num * num)
               .forEach(System.out::println);

        // Example 3: Reducing numbers to their sum
        int sum = numbers.stream()
                        .reduce(0, Integer::sum);
        System.out.println("Sum: " + sum);
    }
}
```
In this example:

We create a list of integers numbers.
Example 1 demonstrates filtering even numbers using the filter() operation.
Example 2 shows mapping each number to its square using the map() operation.
Example 3 illustrates reducing the numbers to their sum using the reduce() operation.
### Features
Provides a comprehensive understanding of streams in Java.
Clarifies that streams are not storage containers but rather enable efficient processing of data elements.
Offers examples of common stream operations including filtering, mapping, and reducing.

## Introduction to Streams Pipeline
Streams Pipeline is a powerful feature introduced in Java 8, allowing developers to perform complex data processing tasks with concise and expressive code.

### What is Streams Pipeline?
Streams Pipeline is a sequence of aggregate operations (such as filter, map, reduce, etc.) that are applied to a stream of elements to perform a specific task. It enables functional-style operations on collections, making code more readable, concise, and efficient.

### Key Concepts
Stream: Represents a sequence of elements and supports aggregate operations.
Intermediate Operations: Operations such as filter, map, sorted, etc., which transform a stream into another stream. These operations are lazy and do not produce any result until a terminal operation is executed.
Terminal Operations: Operations such as forEach, collect, reduce, etc., which produce a result or side-effect. Terminal operations trigger the execution of the intermediate operations.
Stateless vs. Stateful Operations: Stateless operations do not rely on the state of other elements in the stream, whereas stateful operations may depend on the state of other elements.
### Getting Started
To use Streams Pipeline in your Java project:

Ensure you have Java 8 or later installed on your system.
Create a new Java project or open an existing one.
Import the necessary packages:
```java
import java.util.stream.Stream;
```
Start using Streams Pipeline in your code.
### Examples
Filtering elements
```java
List<String> names = Arrays.asList("John", "Alice", "Bob", "David");
// Filter names starting with 'A'
names.stream()
     .filter(name -> name.startsWith("A"))
     .forEach(System.out::println);
```
### Mapping elements
```java
List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);

// Square each number
numbers.stream()
       .map(n -> n * n)
       .forEach(System.out::println);
```
### Reducing elements
```java
List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);

// Sum of all numbers
int sum = numbers.stream()
                 .reduce(0, Integer::sum);
System.out.println("Sum: " + sum);
```

## Java Streams `map()` Function
In Java, Streams provide a convenient and efficient way to work with sequences of elements. The `map()` function is one of the most frequently used functions in Streams. It transforms each element of the stream using the provided function and returns a new stream consisting of the transformed elements.

### Syntax

The syntax of the `map()` function in Java Streams is as follows:

```java
<R> Stream<R> map(Function<? super T,? extends R> mapper);
```

Here,

`Function<? super T,? extends R> mapper`: A functional interface that represents a function that accepts one argument of type T and produces a result of type R. This function is applied to each element of the stream.
### Parameters
- **mapper :** The function to apply to each element of the stream.
### Return Value
- The `map()` function returns a new Stream consisting of the results of applying the given function to the elements of this stream.

### Example
```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;


public class Main {
    public static void main(String[] args) {
        List<String> names = Arrays.asList("John", "Alice", "Bob", "Eve");

        // Convert each name to uppercase
        List<String> upperCaseNames = names.stream()
                                          .map(String::toUpperCase)
                                          .collect(Collectors.toList());

        System.out.println(upperCaseNames); // Output: [JOHN, ALICE, BOB, EVE]
    }
}
```
In this example, the map() function is used to convert each name in the names list to uppercase.

### Common Use Cases
- **Transformation :** Transforming elements of a stream from one type to another.
- **Data Manipulation :** Applying a function to each element to derive a new value or perform some operation.
### Advantages
- **Concise :** Allows concise and readable code for transforming elements of a stream.
- **Pipeline Friendly :** Fits well into stream pipelines, enabling powerful data processing operations.
### Conclusion
The `map()` function in Java Streams is a powerful tool for transforming elements of a stream according to a specified function. It promotes functional programming practices and enables elegant and efficient data processing operations.

## Java Streams `flatMap()` Function
In Java, Streams provide a powerful way to work with sequences of elements. The `flatMap()` function is a versatile tool that allows flattening of nested collections or streams within a stream, resulting in a single stream of elements.

### Syntax

The syntax of the `flatMap()` function in Java Streams is as follows:

```java
<R> Stream<R> flatMap(Function<? super T,? extends Stream<? extends R>> mapper);
```

Here,

`Function<? super T,? extends Stream<? extends R>> mapper`: A functional interface that represents a function that accepts one argument of type T and produces a stream of elements of type R. This function is applied to each element of the stream.
### Parameters
**mapper :** The function to apply to each element of the stream, which returns a stream of elements.
### Return Value
 -The `flatMap()` function returns a new Stream consisting of the results of replacing each element of this stream with the contents of a mapped stream produced by applying the provided mapping function to each element.

### Example
```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class Main {
    public static void main(String[] args) {
        List<List<Integer>> nestedLists = Arrays.asList(
            Arrays.asList(1, 2, 3),
            Arrays.asList(4, 5, 6),
            Arrays.asList(7, 8, 9)
        );

        // Flatten the nested lists into a single list
        List<Integer> flattenedList = nestedLists.stream()
                                                 .flatMap(List::stream)
                                                 .collect(Collectors.toList());

        System.out.println(flattenedList); // Output: [1, 2, 3, 4, 5, 6, 7, 8, 9]
    }
}
```
In this example, the `flatMap()` function is used to flatten a list of lists into a single list.

### Common Use Cases
- **Flattening :** Flattening a stream of collections or streams into a single stream.
- **Removing Empty Elements :** Filtering out empty or null elements from a stream.
 -**Converting :** Converting a complex structure into a simpler one.
### Advantages
- **Streamlining Data Processing :** Simplifies data processing by flattening nested structures.
- **Versatility :** Offers a wide range of applications, from flattening collections to filtering out empty elements.
### Conclusion
The `flatMap()` function in Java Streams is a powerful tool for flattening nested collections or streams within a stream, allowing for streamlined data processing and transformation. It promotes concise and readable code and enables efficient manipulation of complex data structures.



