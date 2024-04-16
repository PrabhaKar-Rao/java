# Streams 📚
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

### Example 💡
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
### Conclusion 🎉
Creating Streams from collections in Java is straightforward and allows for concise and expressive code. Streams provide powerful features for processing data in a functional style.

## Streams have no Storage
Streams in Java are not data storage containers; instead, they provide a way to process elements from a source (such as a collection, array, or I/O channel) in a functional and declarative style. Streams operate on data elements in a sequence and allow for various operations to be performed on those elements, such as filtering, mapping, sorting, and reducing.

### Example 💡
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

- We create a list of integers numbers.
- Example 1 demonstrates filtering even numbers using the filter() operation.
- Example 2 shows mapping each number to its square using the map() operation.
- Example 3 illustrates reducing the numbers to their sum using the reduce() operation.
### Features 🚀
- Provides a comprehensive understanding of streams in Java.
- Clarifies that streams are not storage containers but rather enable efficient processing of data elements.
- Offers examples of common stream operations including filtering, mapping, and reducing.

## Introduction to Streams Pipeline
Streams Pipeline is a powerful feature introduced in Java 8, allowing developers to perform complex data processing tasks with concise and expressive code.

### What is Streams Pipeline?
Streams Pipeline is a sequence of aggregate operations (such as filter, map, reduce, etc.) that are applied to a stream of elements to perform a specific task. It enables functional-style operations on collections, making code more readable, concise, and efficient.

### Key Concepts 🚀
- **Stream :** Represents a sequence of elements and supports aggregate operations.
- **Intermediate Operations :** Operations such as filter, map, sorted, etc., which transform a stream into another stream. These operations are lazy and do not produce any result until a terminal operation is executed.
- **Terminal Operations :** Operations such as forEach, collect, reduce, etc., which produce a result or side-effect. Terminal operations trigger the execution of the intermediate operations.
- **Stateless vs. Stateful Operations :** Stateless operations do not rely on the state of other elements in the stream, whereas stateful operations may depend on the state of other elements.
### Getting Started
To use Streams Pipeline in your Java project:

Ensure you have Java 8 or later installed on your system.
Create a new Java project or open an existing one.
Import the necessary packages:
```java
import java.util.stream.Stream;
```
Start using Streams Pipeline in your code.
### Examples 💡
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

### Example 💡
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
### Conclusion 🎉
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

### Example 💡
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
### Conclusion 🎉
The `flatMap()` function in Java Streams is a powerful tool for flattening nested collections or streams within a stream, allowing for streamlined data processing and transformation. It promotes concise and readable code and enables efficient manipulation of complex data structures.

## Java Streams `filter()` Function

In Java, Streams provide a convenient way to work with sequences of elements. The `filter()` function is used to select elements from a stream based on a specified condition.

### Syntax

The syntax of the `filter()` function in Java Streams is as follows:

```java
Stream<T> filter(Predicate<? super T> predicate)
```
Here,

- ** Predicate<? super T> predicate :** A functional interface that represents a predicate (boolean-valued function) of one argument. The function returns true if the input argument matches the condition, otherwise false.
### Parameters
- **predicate :** The predicate to apply to each element of the stream. Only elements that satisfy the predicate will be included in the resulting stream.
### Return Value
- The `filter()` function returns a new Stream consisting of the elements that match the given predicate.

### Example 💡
```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class Main {
    public static void main(String[] args) {
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);

        // Filter even numbers
        List<Integer> evenNumbers = numbers.stream()
                                           .filter(n -> n % 2 == 0)
                                           .collect(Collectors.toList());

        System.out.println(evenNumbers); // Output: [2, 4, 6, 8, 10]
    }
}
```
In this example, the `filter()` function is used to select only the even numbers from the numbers list.

### Common Use Cases 🚀
- **Data Filtering :** Filtering elements based on specified criteria.
- **Condition-based Selection :** Selecting elements that meet certain conditions.
- **Data Cleaning :** Removing unwanted elements or outliers from a stream.
### Advantages 🚀
- **Flexible Filtering :** Provides a flexible way to filter elements based on arbitrary conditions.
- **Readability :** Improves code readability by clearly expressing the filtering criteria.
- Performance :** Can lead to performance improvements by reducing the number of elements to process.
### Conclusion 🎉
The `filter()` function in Java Streams is a powerful tool for selecting elements from a stream based on specified criteria. It promotes clean and expressive code and enables efficient data filtering and selection operations.

## Java Streams `limit()` Function
In Java, Streams provide a convenient way to work with sequences of elements. The `limit()` function is used to reduce the size of a stream to a specified maximum number of elements.

### Syntax

The syntax of the `limit()` function in Java Streams is as follows:

```java
Stream<T> limit(long maxSize);
```

Here,
- **maxSize :** The maximum number of elements the resulting stream should contain.
### Parameters
- **maxSize :** The maximum number of elements to be present in the resulting stream.
### Return Value
- The `limit() function returns a new Stream consisting of the first maxSize elements of the original stream.

### Example 💡
```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class Main {
    public static void main(String[] args) {
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);

        // Limit to first 5 elements
        List<Integer> limitedNumbers = numbers.stream()
                                              .limit(5)
                                              .collect(Collectors.toList());

        System.out.println(limitedNumbers); // Output: [1, 2, 3, 4, 5]
    }
}
```
In this example, the limit() function is used to restrict the stream to the first 5 elements of the numbers list.

### Common Use Cases
- **Pagination :** Limiting the number of elements displayed on a page.
- **Performance Optimization :** Reducing processing time by limiting the number of elements processed.
- **Sampling :** Extracting a subset of elements for analysis or testing.
### Advantages 🚀
**Control :** Provides control over the size of the stream, allowing for efficient memory usage.
**Performance Optimization :** Can lead to performance improvements by reducing the number of elements processed.
**Tailoring Output :** Allows tailoring the output to specific requirements, such as display limitations.
### Conclusion 🎉
The `limit()` function in Java Streams is a useful tool for restricting the size of a stream to a specified maximum number of elements. It promotes efficient data processing and enables tailored output based on specific requirements.

## Java Streams `skip()` Function
In Java, Streams provide a convenient way to work with sequences of elements. The `skip()` function is used to bypass a specified number of elements in a stream, returning a new stream without those elements.

### Syntax

The syntax of the `skip()` function in Java Streams is as follows:

```java
Stream<T> skip(long n);
```

Here,

- `n `: The number of elements to skip.
### Parameters
- `n `: The number of elements to bypass in the stream.
### Return Value
The `skip()` function returns a new Stream consisting of the remaining elements of the original stream after skipping the specified number of elements.

### Example 💡
```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class Main {
    public static void main(String[] args) {
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);

        // Skip the first 5 elements
        List<Integer> remainingNumbers = numbers.stream()
                                                .skip(5)
                                                .collect(Collectors.toList());

        System.out.println(remainingNumbers); // Output: [6, 7, 8, 9, 10]
    }
}
```
In this example, the `skip()` function is used to skip the first 5 elements of the numbers list and return the remaining elements.

### Common Use Cases
- **Pagination :** Skipping elements for displaying results on subsequent pages.
- **Data Skimming :** Bypassing irrelevant or unwanted elements from the beginning of a stream.
- **Data Transformation :** Pre-processing data by skipping initial records or headers.
### Advantages 🚀
**Flexibility :** Provides flexibility in skipping a specific number of elements from the beginning of a stream.
**Efficient Data Processing :** Enables efficient processing of large datasets by skipping unnecessary initial elements.
**Tailoring Output :** Allows tailoring the output to specific requirements by excluding irrelevant data.
### Conclusion 🎉
The `skip()` function in Java Streams is a valuable tool for bypassing a specified number of elements in a stream, enabling efficient data processing and tailored output based on specific requirements.

## Java Streams `reduce()` Function
n Java, Streams provide a powerful way to work with sequences of elements. The `reduce()` function is used to combine the elements of a stream into a single result by applying a binary operator.

### Syntax

The syntax of the `reduce()` function in Java Streams is as follows:

```java
Optional<T> reduce(BinaryOperator<T> accumulator);
```
or

```java
T reduce(T identity, BinaryOperator<T> accumulator);
```

Here,

- **accumulator **: A BinaryOperator that combines two values into a single value.
Parameters
- **accumulator :** The binary operator used to accumulate the elements of the stream.

- **identity :** The initial value of the accumulation.

### Return Value
- The `reduce()` function returns an Optional or the accumulated result of applying the binary operator to the elements of the stream.

### Example
```java
import java.util.Arrays;
import java.util.List;
import java.util.Optional;

public class Main {
    public static void main(String[] args) {
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);

        // Example 1: Reduce to sum of elements
        Optional<Integer> sum = numbers.stream()
                                       .reduce(Integer::sum);

        System.out.println("Sum: " + sum.orElse(0)); // Output: Sum: 15

        // Example 2: Reduce with initial value (10) to find the product
        Integer product = numbers.stream()
                                .reduce(10, (a, b) -> a * b);

        System.out.println("Product: " + product); // Output: Product: 1200
    }
}
```
In Example 1, the `reduce()` function is used to calculate the sum of all elements in the numbers list. In Example 2, the `reduce()` function with an initial value is used to find the product of all elements in the list.

### Common Use Cases
- **Aggregation :** Combining elements of a stream into a single result, such as summing or multiplying.
- **Custom Reduction :** Performing custom reduction operations on stream elements.
- **Data Analysis :** Calculating statistical measures or aggregating data.
### Advantages
- **Powerful Aggregation :** Enables powerful aggregation operations on stream elements.
- **Flexibility :** Provides flexibility in defining custom reduction operations.
- **Error Handling :** Returns an Optional to handle scenarios where the stream is empty.
### Conclusion
The `reduce()` function in Java Streams is a versatile tool for aggregating the elements of a stream into a single result. It supports various aggregation operations and provides flexibility in defining custom reduction logic, making it a fundamental building block for stream processing tasks.

## Java Streams `collect()` Function
In Java, Streams provide a powerful way to work with sequences of elements. The `collect()` function is used to accumulate the elements of a stream into a collection or a single value.

### Syntax

The syntax of the `collect()` function in Java Streams is as follows:

```java
<R,A> R collect(Collector<? super T,A,R> collector);
```

Here,

- **collector :** A Collector that describes how to accumulate elements into a result container.
Parameters
- **collector :** The collector that specifies the way elements are collected into the result.
### Return Value
- The `collect()` function returns the result of the accumulation, which can be of any type specified by the collector.

### Example
```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class Main {
    public static void main(String[] args) {
        List<String> words = Arrays.asList("apple", "banana", "cherry");

        // Example 1: Collect elements into a List
        List<String> collectedList = words.stream()
                                         .collect(Collectors.toList());

        System.out.println("Collected List: " + collectedList); // Output: Collected List: [apple, banana, cherry]

        // Example 2: Concatenate elements into a single String
        String concatenatedString = words.stream()
                                        .collect(Collectors.joining(", "));

        System.out.println("Concatenated String: " + concatenatedString); // Output: Concatenated String: apple, banana, cherry
    }
}
```
In Example 1, the `collect()` function is used to accumulate elements into a List. In Example 2, it's used to concatenate elements into a single String separated by commas.

### Common Use Cases
- **Collection Creation :** Accumulating elements into collections such as List, Set, or Map.
- **String Concatenation :** Joining elements into a single String with a specified delimiter.
 -**Custom Accumulation :** Performing custom accumulation operations based on specific requirements.
### Advantages
- **Flexible Collection :** Provides flexibility in accumulating elements into various types of collections.
- **Concise Code :** Allows concise and readable code for collecting and processing stream elements.
- **Efficient Data Handling :** Offers efficient handling of large datasets by accumulating elements in a single operation.
### Conclusion
The `collect()` function in Java Streams is a versatile tool for accumulating elements of a stream into a collection or a single value. It supports various collection types and customization options, making it a fundamental operation for stream processing tasks.

