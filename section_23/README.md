# Date and Time 📚
Java offers comprehensive support for handling date and time through its built-in libraries in the `java.time` package. This package was introduced in Java 8 as part of the Java Date and Time API (JSR 310), providing a modern, flexible, and thread-safe API for working with dates and times.
## Why new Date API introduced in Java 8 🤔
The new Date and Time API introduced in Java 8, also known as the `java.time` package, addressed several limitations and issues present in the older `java.util.Date` and `java.util.Calendar` classes. Here are some reasons why the new API was introduced:
**Immutability :** Objects in the `java.time` package are immutable, meaning their state cannot be modified after creation. This ensures thread safety, simplifies concurrency, and reduces the risk of unintended side effects.

**Clarity and Readability :** The new API provides clearer and more intuitive class names like `LocalDate`, `LocalTime`, and `ZonedDateTime`, making code more readable and expressive compared to the ambiguous `Date` and `Calendar` classes.

**Null-Safe :** The old API had issues with null values and was prone to `NullPointerExceptions`. The new API is designed to handle null values more gracefully, reducing the risk of runtime errors.

**Consistency :** The old API had inconsistent and error-prone methods for date and time manipulation. The new API provides consistent and comprehensive methods for various date and time operations, reducing the complexity of code and improving maintainability.

**Interoperability :** The new API is designed to work seamlessly with other modern Java features such as lambdas, streams, and the java.time.temporal package. This improves interoperability and makes it easier to integrate date and time functionality with other parts of the Java ecosystem.

**Localization Support :** The new API provides better support for internationalization and localization, allowing developers to format and parse dates and times according to different locales and languages.

**Better Time Zone Handling :** The old API had limited support for time zones and often led to errors and inconsistencies when working with different time zones. The new API provides robust support for time zones, including the `ZoneId` and `ZonedDateTime` classes, making it easier to handle date and time calculations across different time zones.

Overall, the introduction of the new Date and Time API in Java 8 aimed to address the shortcomings of the old API, providing a more modern, robust, and developer-friendly solution for working with dates and times in Java applications.

## java.util.Date
The `java.util.Date` class represents a specific instant in time, with millisecond precision. It is widely used in Java applications for handling dates and times. However, it's important to note that this class has been largely superseded by the `java.time` package in Java 8 and later versions. Nevertheless, understanding its usage can still be beneficial, especially when dealing with legacy codebases.
### Example  💡

Here's a simple example demonstrating some common operations with `java.util.Date`:

```java
import java.util.Date;

public class DateDemo {
    public static void main(String[] args) {
        // Create a new Date object representing the current date and time
        Date currentDate = new Date();

        // Print the current date and time
        System.out.println("Current Date and Time: " + currentDate);

        // Get the milliseconds since January 1, 1970, 00:00:00 GMT
        long milliseconds = currentDate.getTime();
        System.out.println("Milliseconds since January 1, 1970: " + milliseconds);

        // Set the time of the date object to a specific timestamp
        Date specificDate = new Date(1617888000000L); // April 9, 2021, 00:00:00 GMT
        System.out.println("Specific Date: " + specificDate);

        // Compare two dates
        if (currentDate.after(specificDate)) {
            System.out.println("The current date is after the specific date.");
        } else if (currentDate.before(specificDate)) {
            System.out.println("The current date is before the specific date.");
        } else {
            System.out.println("The current date is equal to the specific date.");
        }

        // Check if a date is equal to another date
        if (currentDate.equals(specificDate)) {
            System.out.println("The current date is equal to the specific date.");
        } else {
            System.out.println("The current date is not equal to the specific date.");
        }
    }
}
```
## Date Formatting and Parsing using SimpleDateFormat
Formatting dates involves converting a `Date` object into a string representation according to a specified pattern, while parsing dates involves converting a string representation of a date into a `Date` object.

### Formatting Dates

To format a date into a string representation, follow these steps:

1. Create a `SimpleDateFormat` object with the desired date pattern.
2. Call the `format()` method on the `SimpleDateFormat` object, passing the `Date` object you want to format.

#### Example:
```java
import java.text.SimpleDateFormat;
import java.util.Date;

public class DateFormattingExample {
    public static void main(String[] args) {
        Date currentDate = new Date();
        SimpleDateFormat formatter = new SimpleDateFormat("dd-MM-yyyy HH:mm:ss");
        String formattedDate = formatter.format(currentDate);
        System.out.println("Formatted Date: " + formattedDate);
    }
}
```

### Parsing Dates
To parse a string representation of a date into a Date object, follow these steps:

- Create a `SimpleDateFormat` object with the date pattern matching the format of the string representation.
- Call the `parse()` method on the `SimpleDateFormat` object, passing the string representation of the date.
#### Example:

```java
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;

public class DateParsingExample {
    public static void main(String[] args) {
        String dateString = "08-04-2024 14:30:00";
        SimpleDateFormat formatter = new SimpleDateFormat("dd-MM-yyyy HH:mm:ss");
        try {
            Date parsedDate = formatter.parse(dateString);
            System.out.println("Parsed Date: " + parsedDate);
        } catch (ParseException e) {
            e.printStackTrace();
        }
    }
}
```
### Date Patterns
You can use various patterns to format and parse dates according to your requirements. Some commonly used patterns include:

- `dd` - Day of the month (01-31)
- `MM` - Month in year (01-12)
- `yyyy` - Year (e.g., 2024)
- `HH` - Hour in day (00-23)
- `mm` - Minute in hour (00-59)
- `ss` - Second in minute (00-59)

