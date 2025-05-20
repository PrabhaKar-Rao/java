# New Features of java 22
## Multi-file source code programs
A "multiple source code program" in Java typically refers to a Java program that consists of multiple source code files. In Java, a program can be divided into multiple source files, each containing a class or a group of related classes. These source files are then compiled separately and combined into a single executable or library.

Here's a brief explanation of how a multiple source code program works in Java:

- **Organizing Code :** In larger Java projects, it's common to organize code into multiple files for better maintainability and readability. Each file typically contains one or more related classes.
- **Compilation :** Each source code file (.java file) is compiled into a corresponding bytecode file (.class file) using the Java compiler (javac). For example, if you have Main.java, Class1.java, and Class2.java, each will be compiled into Main.class, Class1.class, and Class2.class, respectively.
- **Dependencies :** If one class depends on another, you import it using the import statement at the beginning of your source file. This allows you to use classes and interfaces defined in other source files.
- **Execution :** When you run the program, you typically specify the main class that contains the `main()` method. Java runtime (java) loads the necessary classes and executes the program.

## Unnamed variables and patterns

Unnamed variables are variables that can be initialized but not used. Unnamed patterns can appear in a pattern list of a record pattern, and always match the corresponding record component. You can use them instead of a type pattern. They remove the burden of having to write a type and name of a pattern variable that's not needed in subsequent code. You denote both with the underscore character (_).

For background information about unnamed variables and patterns, see JEP 456.

### Unnamed Variables

You can use the underscore keyword `(_)` as the name of a local variable, exception, or lambda parameter in a declaration when the value of the declaration isn't needed. This is called an unnamed variable, which represents a variable that’s being declared but it has no usable name.

Unnamed variables are useful when the side effect of a statement is more important than its result.

#### Example

```java
package com.eazybytes.java22;

import java.io.BufferedReader;
import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.IOException;
import java.util.Arrays;
import java.util.List;
import java.util.Map;
import java.util.stream.Collectors;

public class UnnamedVariables {

    public static void main(String[] args) {
        // Scenario 1
        List<String> wordList = Arrays.asList("apple", "banana", "orange", "grape", "kiwi");
        int totalWords = countWords(wordList);
        System.out.println(totalWords);

        // Scenario 2
        List<String> fruits = Arrays.asList("apple", "banana", "orange");
        Map<String, String> fruitMap = fruits.stream()
                .collect(Collectors.toMap(f -> f, _ -> "Fruit"));
        System.out.println(fruitMap);

        // Scenario 3
        boolean isValid = convertAndDisplay("45");

        // Scenario 4
        executeIfFilePresent();

        // Scenario 5
        Point point = new Point(7, 3);
        if (point instanceof Point(int x, _)) {
            // Only use the 'x' property from the Point record
            System.out.printf("Point object with value of x: %d%n", x);
        }
    }

    public static int countWords(Iterable<String> words) {
        int totalWords = 0;
        for (String _ : words) {
            totalWords++;
        }
        return totalWords;
    }

    public static boolean convertAndDisplay(String input) {
        boolean isValid;
        try{
            int _ = Integer.parseInt(input);
            isValid = true;
        }catch (NumberFormatException _) {
            System.out.println("NumberFormatException due to invalid input: " + input);
            isValid = false;
        }catch (Exception _) {
            System.out.println("Exception due to invalid input: " + input);
            isValid = false;
        }
        return isValid;
    }

    public static void executeIfFilePresent() {
        String filePath = "example.txt";
        try(BufferedReader _ = new BufferedReader(new FileReader(filePath));){
            System.out.println("Executing some logic");
        } catch (FileNotFoundException _) {
            System.out.println("FileNotFoundException");
        } catch (IOException _) {
            System.out.println("IOException");
        }
    }

}

record Point(int x, int y) { }

```
```java
package com.eazybytes.java22;

public class UnnamedPatterns {

    public static void main(String[] args) {
        Vehicle vehicle = new Truck("Toyota");

        switch (vehicle) {
            case Car _ -> processCar(vehicle);
            case Bike _ -> processBike(vehicle);
            case Truck _ -> processTruck(vehicle);
        }
    }

    public static void processCar(Vehicle vehicle) {
        if(vehicle instanceof Car car) {
            System.out.println("Processing car model: " + car.getModel());
        }
    }

    public static void processBike(Vehicle vehicle) {
        if(vehicle instanceof Bike bike) {
            System.out.println("Processing bike brand: " + bike.getBrand());
        }
    }

    public static void processTruck(Vehicle vehicle) {
        if(vehicle instanceof Truck truck) {
            System.out.println("Processing truck manufacturer: " + truck.getManufacturer());
        }
    }

}
```
```java
package com.eazybytes.java22;

public sealed interface Vehicle permits Car, Bike, Truck {

}

final class Bike implements Vehicle {
    private final String brand;

    public Bike(String brand) {
        this.brand = brand;
    }

    public String getBrand() {
        return brand;
    }
}

final class Car implements Vehicle {
    private final String model;

    public Car(String model) {
        this.model = model;
    }

    public String getModel() {
        return model;
    }
}

final class Truck implements Vehicle {
    private final String manufacturer;

    public Truck(String manufacturer) {
        this.manufacturer = manufacturer;
    }

    public String getManufacturer() {
        return manufacturer;
    }
}
```
# 📘 Java 23 Feature: Markdown Documentation Comments (Preview)
Java 23 introduces support for Markdown syntax inside Javadoc comments using the @-style JavaDoc tool, making documentation easier to write and more readable.

✅ This feature is available as a preview and must be enabled using the --enable-preview compiler option.

✅ Key Points
Markdown syntax can now be used in Javadoc comments (e.g., **bold**, _italic_, lists, code blocks).

This improves readability and integrates well with modern documentation tools.

It allows a better developer experience and enhances API documentation quality.
## ✏️ Example
```java
  /** Markdown in Javadoc
 
  This method adds two integers.
 
  Parameters
  - `a`: First number
  - `b`: Second number
 
  Returns
  The sum of `a` and `b`.
 
  Example **/
   

int result = add(10, 20);
public class Calculator {
    public int add(int a, int b) {
        return a + b;
    }
}
```

## 🚀 How to Compile with Preview Features
```java
javac --enable-preview --release 23 Calculator.java
```
## 📚 Output in Javadoc
```java
javadoc --enable-preview --release 23 Calculator.java
```
The output will render your Javadoc with Markdown formatting like:

- Headers (e.g., #, ##)

- Code blocks

- Lists and inline formatting

 ## 🚀 Java 24 Features: Stream Gatherers API

Java 24 introduces the **Stream Gatherers API**, expanding the Java Stream capabilities with powerful intermediate operations that allow custom data grouping and transformation.



## 📘  Introduction to Stream Gatherers API

The **Gatherers API** in Java 24 enhances the Stream pipeline by enabling more expressive and stateful transformations in the middle of a stream.  
Think of it as a customizable version of `map()` or `flatMap()`—but with more power!

> ✅ This feature is part of the Java 24 preview and requires `--enable-preview`.



## 🧩 Getting to Know the Basic Syntax of `Gatherer` Interface

The `Gatherer<T, A, R>` interface allows you to define:
- `T`: Input element type
- `A`: Accumulation state type
- `R`: Result type emitted to the downstream

### 🧪 Example:

```java
Gatherer<String, ?, String> toUpper = Gatherer.ofSequential(
    () -> Gatherer.Sink.ofConsumer(s -> s.toUpperCase())
);
```
- 🔍 This basic Gatherer will convert each string to uppercase.
  
### 🛠️  Using Gatherer.of() to Create an Intermediate Operation
The `Gatherer.of()` and `Gatherer.ofSequential()` methods are used to define custom intermediate operations. These can act similarly to map() or batch-wise transformation using `flatMap()`.

### 🧪 Example: Custom Batch Gatherer
```java
import java.util.stream.*;
import java.util.stream.Gatherers;
import java.util.List;

public class GathererDemo {
    public static void main(String[] args) {
        List<String> result = Stream.of("a", "b", "c", "d", "e")
            .gather(Gatherers.windowFixed(2))
            .map(window -> String.join("-", window))
            .toList();

        System.out.println(result); // Output: [a-b, c-d, e]
    }
}

```
### 📌 Output:
```java
[a-b, c-d, e]
```
### 🔍 Explanation:
- `Gatherers.windowFixed(2)` splits elements into windows of size 2.

- `map()` combines them with a dash `(-)` separator.

- The output shows string batches combined.

### 📎 Notes
- Gatherers provide fine-grained control over intermediate stream processing.

- Use this feature in preview mode:

```java
javac --enable-preview --release 24 GathererDemo.java
java --enable-preview GathererDemo
```


## 🧠 Gatherers with Mutable State & Initializer

Gatherers allow the use of a **mutable container** (like `StringBuilder`, `List`, or `Map`) to accumulate state across elements.

### 🧪 Example: Group characters into 3-letter words

```java
import java.util.stream.*;
import java.util.stream.Gatherers;
import java.util.*;

public class GathererStateDemo {
    public static void main(String[] args) {
        List<String> result = Stream.of("a", "b", "c", "d", "e", "f", "g")
            .gather(Gatherer.of(
                () -> new StringBuilder(),  // Initializer (creates mutable state)
                (sb, s, downstream) -> {
                    sb.append(s);
                    if (sb.length() == 3) {
                        downstream.push(sb.toString()); // Send result downstream
                        sb.setLength(0); // Reset state
                    }
                },
                (sb, downstream) -> {
                    if (sb.length() > 0) {
                        downstream.push(sb.toString()); // Finish remaining chars
                    }
                }
            ))
            .toList();

        System.out.println(result); // Output: [abc, def, g]
    }
}
```

### 🧾 Explanation

| Part                              | What It Does                               |
| --------------------------------- | ------------------------------------------ |
| `() -> new StringBuilder()`       | **Initializer**: Sets up the mutable state |
| Accumulator `(sb, s, downstream)` | Adds characters and pushes when ready      |
| Finisher `(sb, downstream)`       | Pushes any leftover data at the end        |

## 🎯  Finisher in a Stream Gatherer
The finisher is optional but crucial when the remaining state may contain useful data at the end of the stream. It ensures that no data is lost during stream processing.

 📌 Without a finisher, any "incomplete" batches (like a group of 1 or 2 characters in a 3-char gatherer) would be discarded.

### 🛠️ Compile and Run
Make sure to enable preview features when compiling:
```java
javac --enable-preview --release 24 GathererStateDemo.java
java --enable-preview GathererStateDemo
```
### 📚 Summary
| Concept     | Description                                     |
| ----------- | ----------------------------------------------- |
| Initializer | Prepares mutable state (e.g., a buffer or list) |
| Accumulator | Handles element-by-element logic                |
| Finisher    | Final cleanup or output of remaining state      |

#### 💡 Use Cases:

- Batching data
- Grouping elements
- Stateful filtering
- Windowed aggregations


## 📘  Parallel Gatherers

Parallel Gatherers enable **stateful intermediate operations** to be executed in parallel without violating the ordering and correctness of the stream.

### 🔍 Key Concepts

- **Thread-safety**: Each parallel task uses its own mutable state.
- **Split behavior**: The `Gatherer` is designed to operate correctly when the stream is split across threads.
- **Finisher**: Ensures that residual state from each parallel thread is passed downstream.

> ⚠️ Parallel gatherers must **not** share mutable state unless it is properly synchronized.

## 🔬 When to Use

- Large-scale stream processing
- Custom parallel batching or windowing
- Parallel grouping of elements (e.g., words, logs, events)

### 🔧 Example Code

```java
import java.util.stream.*;
import java.util.stream.Gatherers;
import java.util.*;

public class ParallelGathererDemo {
    public static void main(String[] args) {
        List<String> result = Stream.of("a", "b", "c", "d", "e", "f")
            .parallel() // Run the stream in parallel
            .gather(Gatherer.of(
                () -> new ArrayList<String>(), // initializer
                (list, item, downstream) -> {
                    list.add(item);
                    if (list.size() == 2) {
                        downstream.push(String.join("-", list));
                        list.clear();
                    }
                },
                (list, downstream) -> {
                    if (!list.isEmpty()) {
                        downstream.push(String.join("-", list));
                    }
                }
            ))
            .toList();

        System.out.println(result);
    }
}
```
- 💡 Note: The order may vary due to parallel processing!

### 🧾 Explanation

| Component          | Purpose                                               |
| ------------------ | ----------------------------------------------------- |
| `parallel()`       | Enables parallel stream processing                    |
| `Gatherer.of(...)` | Defines how to group in batches                       |
| `Finisher`         | Handles any leftover elements in each parallel thread |

### ⚙️ Compile and Run
```java
javac --enable-preview --release 24 ParallelGathererDemo.java
java --enable-preview ParallelGathererDemo
```
- ✅ Ensure your system has multiple cores to take advantage of parallelism.

### 📚 Summary
| Concept              | Description                                   |
| -------------------- | --------------------------------------------- |
| Parallel Gatherers   | Allows gatherers to work on parallel streams  |
| Independent State    | Each task maintains its own buffer/state      |
| Final Finisher Phase | Combines leftover results per parallel thread |

🔥 Java 24 is pushing boundaries in Stream API performance and flexibility. Parallel Gatherers are especially useful when working with large data pipelines!


## ⚡ Interrupting & Chaining Gatherers

You can **interrupt** a Gatherer chain using custom logic (e.g., break on a condition), and you can also **chain multiple Gatherers** together to build layered processing flows.

### 🔧 Example: Interrupt stream when an element equals "STOP"

```java
import java.util.stream.*;
import java.util.stream.Gatherers;
import java.util.*;

public class InterruptAndChainDemo {
    public static void main(String[] args) {
        List<String> result = Stream.of("one", "two", "STOP", "three")
            .gather(Gatherers.<String>filtering(s -> !s.equals("STOP")))
            .gather(Gatherers.mapping(String::toUpperCase))
            .toList();

        System.out.println(result); // Output: [ONE, TWO, THREE]
    }
}
```
- 💡 Use filtering and mapping to chain logic like a pipeline.

### 🔁  `fold()`, `scan()`, `mapConcurrent()` Methods
🔹 `fold(identity, accumulator)`
Accumulates all items like reduce, but emits only the final result.

🔹 `scan(identity, accumulator)`
Like fold, but emits the intermediate result after every element.

🔹 `mapConcurrent(fn)`
Maps elements in parallel, useful for heavy transformation tasks.

### 🧪 Example: Using scan() to track running total
```java
import java.util.stream.*;
import java.util.stream.Gatherers;
import java.util.*;

public class ScanDemo {
    public static void main(String[] args) {
        List<Integer> result = Stream.of(1, 2, 3, 4)
            .gather(Gatherers.scan(0, Integer::sum))
            .toList();

        System.out.println(result); // Output: [1, 3, 6, 10]
    }
}
```
### 🪟 `windowFixed()` and `windowSliding()`
These gatherers help group elements into fixed-size or sliding windows, just like in time-series processing or real-time analytics.

### 📦 `windowFixed(size)` — Non-overlapping chunks
```java
Stream.of("A", "B", "C", "D", "E")
    .gather(Gatherers.windowFixed(2))
    .toList();
// Output: [[A, B], [C, D], [E]]
```
### 🔄 windowSliding(size, step) — Overlapping windows
```java
Stream.of(1, 2, 3, 4, 5)
    .gather(Gatherers.windowSliding(3, 1))
    .toList();
// Output: [[1,2,3], [2,3,4], [3,4,5]]
```

### ⚙️ Compile and Run
```java
javac --enable-preview --release 24 *.java
java --enable-preview InterruptAndChainDemo
java --enable-preview ScanDemo
```
### 📚 Summary

| Feature                | Description                       |
| ---------------------- | --------------------------------- |
| `filtering`, `mapping` | Interrupting & chaining gatherers |
| `fold()`               | Single result after reduction     |
| `scan()`               | Running total or accumulation     |
| `mapConcurrent()`      | High-performance parallel mapping |
| `windowFixed()`        | Non-overlapping groupings         |
| `windowSliding()`      | Overlapping groupings             |


