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

#### Example 💡
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
#### Example 💡

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
## java.sql.Date
`java.sql.Date` is a class in the Java API that represents a specific instant in time, with millisecond precision, corresponding to SQL `DATE` format. It's a part of the java.sql package, primarily used for database operations where you need to work with dates without time components.

### Features
**Simple Demo :** Demonstrates basic usage of `java.sql.Date`.
**Input Validation :** Validates user input for date values.
**Database Interaction :** Illustrates how `java.sql.Date` can be used in JDBC for database operations.
### Requirements
- Java Development Kit (JDK) 8 or higher.
- Any IDE or text editor for Java development.
- JDBC driver for your database (if you intend to interact with a database).
#### Example 💡
```java
import java.sql.Date;
import java.time.LocalDate;

public class Main {
    public static void main(String[] args) {
        // Create a java.sql.Date object representing today's date
        Date today = new Date(System.currentTimeMillis());
        
        // Display today's date
        System.out.println("Today's date: " + today);
        
        // Add 5 days to today's date
        Date futureDate = addDays(today, 5);
        System.out.println("Date after adding 5 days: " + futureDate);
        
        // Subtract 2 months from today's date
        Date pastDate = subtractMonths(today, 2);
        System.out.println("Date after subtracting 2 months: " + pastDate);
        
        // Check if today's date is before a specific date
        Date comparisonDate = Date.valueOf("2024-05-01");
        boolean isBefore = isBefore(today, comparisonDate);
        System.out.println("Is today's date before " + comparisonDate + "? " + isBefore);
    }
    
    // Method to add days to a given date
    private static Date addDays(Date date, int days) {
        LocalDate localDate = date.toLocalDate().plusDays(days);
        return Date.valueOf(localDate);
    }
    
    // Method to subtract months from a given date
    private static Date subtractMonths(Date date, int months) {
        LocalDate localDate = date.toLocalDate().minusMonths(months);
        return Date.valueOf(localDate);
    }
    
    // Method to check if one date is before another date
    private static boolean isBefore(Date date1, Date date2) {
        return date1.before(date2);
    }
}
```
This example demonstrates adding days, subtracting months, and comparing dates using `java.sql.Date`. Note that java.sql.Date extends `java.util.Date`, so you can use all the methods available in `java.util.Date` as well.

### Conclusion  🎉
In conclusion, the java.sql.Date class in Java is a useful tool for handling date values in applications, particularly in scenarios involving database operations. This demonstration showcased its basic functionalities, including creating instances, performing date arithmetic operations, and comparing dates.

Key takeaways from this example include:

**Creation of Date Instances :** You can create java.sql.Date instances representing specific dates or the current system date.

**Date Manipulations :** Operations such as adding days and subtracting months from a date are straightforward using methods like addDays and subtractMonths.

**Date Comparison :** Comparing dates for order can be done easily with methods like isBefore.

By leveraging these features, developers can effectively manage and manipulate date values in Java applications, ensuring accurate and reliable handling of temporal data.
## java.util.Calendar
`java.util.Calendar` is an abstract class in Java that provides methods for converting between a specific instant in time and a set of calendar fields such as YEAR, MONTH, DAY_OF_MONTH, HOUR, and so on, and for manipulating the calendar fields, such as getting the date of the next week.

### Features
**Date Manipulation :** Allows manipulation of dates and time-related operations.
**Locale-Sensitive :** Calendar computations are locale-sensitive and calendar systems are defined in the `java.util.Locale` class.
**Time Zone Support :** Supports time zone computations and conversions.
**Internationalization :** Provides support for internationalized date and time formats.
### Example 
```java
import java.util.Calendar;

public class Main {
    public static void main(String[] args) {
        // Get a Calendar instance based on the current time in the default time zone and locale.
        Calendar calendar = Calendar.getInstance();

        // Get the current date and time
        System.out.println("Current Date and Time: " + calendar.getTime());

        // Set specific date and time fields
        calendar.set(Calendar.YEAR, 2024);
        calendar.set(Calendar.MONTH, Calendar.APRIL);
        calendar.set(Calendar.DAY_OF_MONTH, 8);
        calendar.set(Calendar.HOUR_OF_DAY, 15);
        calendar.set(Calendar.MINUTE, 30);
        calendar.set(Calendar.SECOND, 0);

        // Get the modified date and time
        System.out.println("Modified Date and Time: " + calendar.getTime());

        // Perform operations like adding or subtracting days
        calendar.add(Calendar.DAY_OF_MONTH, 7);

        // Get the date after adding 7 days
        System.out.println("Date after adding 7 days: " + calendar.getTime());
    }
}
````
### Calender class some operations
### Get Current Date and Time:

```java
Calendar calendar = Calendar.getInstance();
Date currentDate = calendar.getTime();
System.out.println("Current Date and Time: " + currentDate);
```
### Set Specific Date and Time:

```java
calendar.set(Calendar.YEAR, 2024);
calendar.set(Calendar.MONTH, Calendar.APRIL);
calendar.set(Calendar.DAY_OF_MONTH, 8);
calendar.set(Calendar.HOUR_OF_DAY, 15);
calendar.set(Calendar.MINUTE, 30);
calendar.set(Calendar.SECOND, 0);
```
### Add or Subtract Days/Months/Years:

```java
calendar.add(Calendar.DAY_OF_MONTH, 7); // Add 7 days
calendar.add(Calendar.MONTH, -1); // Subtract 1 month
calendar.add(Calendar.YEAR, 2); // Add 2 years
```
### Get Specific Date Components:

```java
int year = calendar.get(Calendar.YEAR);
int month = calendar.get(Calendar.MONTH); // Month starts from 0 (January)
int dayOfMonth = calendar.get(Calendar.DAY_OF_MONTH);
int hour = calendar.get(Calendar.HOUR_OF_DAY);
int minute = calendar.get(Calendar.MINUTE);
int second = calendar.get(Calendar.SECOND);
```
### Get Day of the Week:

```java
int dayOfWeek = calendar.get(Calendar.DAY_OF_WEEK); // Sunday (1) to Saturday (7)
```
### Compare Dates:

```java
Calendar otherCalendar = Calendar.getInstance();
otherCalendar.set(2024, Calendar.APRIL, 8);
int comparison = calendar.compareTo(otherCalendar);
// comparison < 0 if this calendar is before otherCalendar
// comparison == 0 if this calendar is equal to otherCalendar
// comparison > 0 if this calendar is after otherCalendar
```
### Check for Leap Year:

```java
boolean isLeapYear = calendar.getActualMaximum(Calendar.DAY_OF_YEAR) > 365;
```
### Clear Specific Fields:

```java
calendar.clear(Calendar.HOUR_OF_DAY);
```




