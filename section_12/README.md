# Arrays in Java
Arrays in Java are a fundamental data structure used to store a fixed-size sequential collection of elements of the same type. They provide a convenient way to group multiple variables of the same type under a single name.
## Declaration and Initialization
```java
public class Numbers
{
	public static void main(String[] args) {
// Declaration and Initialization 
	int num[]={1,2,3,4};	
}
```
Using the `new` Keyword
```java
public class Numbers
{
	public static void main(String[] args) {
	    
	    int size=5;
      //Declaration
	    int num[] = new int[size];
	    
	    int numbers=1;
	    for(int i=0;i<size;i++){
	        //Initialization
	        num[i]=numbers;
	        numbers++;
	    } 
	}
}
```
## Accessing Elements
Individual elements in an array can be accessed using their index, starting from 0.
```java
int[] numbers = {1, 2, 3, 4, 5};
int firstElement = numbers[0]; // Accessing the first element
int thirdElement = numbers[2]; // Accessing the third element
```
## Array Length
The length of an array can be obtained using the `length` property.
```java
int[] numbers = {1, 2, 3, 4, 5};
int arrayLength = numbers.length; // Returns 5
```
##  Iterating Through Array Elements Using a For Loop 
In Java, you can iterate through the elements of an array using a for loop
###  Example
```java
public class Main {
    public static void main(String[] args) {
        //Approach 1
        int[] numbers = {1, 2, 3, 4, 5};
        System.out.println("Approach 1");
        // Iterating through the array using a for loop
        System.out.println("Iterating through the array elements:");
        for (int i = 0; i < numbers.length; i++) {
            //Accessing elements
            System.out.println("Element at index " + i + ": " + numbers[i]);
        }

       //Approach 2
       int size=5;
       int nums[]=new int[5];
       int digits=1;
       for(int i=0;i<size;i++){
           nums[i]=numbers;
           digits++;
    }
       System.out.println("Approach 2");
      for(int i=0;i<nums.length;i++){
          //Accessing elements
          System.out.println("Element at index " + i + ": " + nums[i]); 
} 
```
#### Output
```java
Approach 1
Iterating through the array elements:
Element at index 0: 1
Element at index 1: 2
Element at index 2: 3
Element at index 3: 4
Element at index 4: 5
Approach 2
Element at index 0: 1
Element at index 1: 2
Element at index 2: 3
Element at index 3: 4
Element at index 4: 5
```
### Explanation
- We declare an array called numbers containing integers.
- We use a for loop to iterate through the array.
- The loop runs from index 0 to `numbers.length - 1`, where `numbers.length` gives the number of elements in the array.
- Inside the loop, we print each element of the array along with its index.
### Conclusion
Iterating through array elements using a for loop in Java is a common and efficient way to access and process each element of an array.
## Iterating Array using For-each Loop
The for-each loop is a simplified way to traverse through arrays and collections in Java, providing a concise and readable syntax.
#### Example
Suppose we have an array of integers named `numbers`. We want to iterate over this array and print each element using the for-each loop.

```java
public class ArrayIteration {
    public static void main(String[] args) {
        int[] numbers = {1, 2, 3, 4, 5};

        // Iterating over the array using for-each loop
        for (int num : numbers) {
            System.out.println(num);
        }
    }
}
```
#### Output
```java
1
2
3
4
5
```
### Conclusion
The for-each loop provides a convenient and concise way to iterate over arrays and collections in Java. It simplifies the syntax and improves code readability, making it a preferred choice for looping through elements.
## Copying Arrays Using Loops
Copying arrays in Java is a common operation in programming. It allows you to create a new array with the same elements as an existing array, which is useful for various tasks such as data manipulation, sorting, and more. By this we can create a new array with required size.
```java
package com.eazybytes.main;

import java.util.Arrays;

public class ArrayCopyDemo {

    public static void main(String[] args) {

        int[] oldArray = {1,2,3,4,5};
        int[] newArray = new int[oldArray.length+5];
        newArray = copyArrayUsingLoop(oldArray, newArray);
      
        for(int num:targetArray1) {
            System.out.println(num);
        }

    }

    private static int[] copyArrayUsingLoop(int[] oldArray, int[] newArray) {
            for(int i = 0; i<oldArray.length;i++){
                newArray[i] = oldArray[i];
            }
            return newArray;
    }
}
```
### Using System.arraycopy() and Arrays.copyOf()
#### Using `System.arraycopy()`
#### Syntax
```java
int[] sourceArray = {1, 2, 3, 4, 5};
int[] destinationArray = new int[sourceArray.length];
System.arraycopy(sourceArray, 0, destinationArray, 0, sourceArray.length);
```
#### Using `Arrays.copyOf()`
```java
int[] sourceArray = {1, 2, 3, 4, 5};
int[] destinationArray = Arrays.copyOf(sourceArray, sourceArray.length);
```
#### Example
```java
package com.eazybytes.main;

import java.util.Arrays;

public class ArrayCopyDemo {

    public static void main(String[] args) {

        int[] oldArray = {1,2,3,4,5};
        int[] newArray = new int[oldArray.length+5];

        System.arraycopy(oldArray, 0, newArray, 0, oldArray.length);
        int[] targetArray = Arrays.copyOf(oldArray,3);

        for(int num:targetArray1) {
            System.out.println(num);
        }

    }
}
```
## Coverting Arrays
The `Arrays` class in Java provides a convenient method `toString()` to convert an array to a string representation. This method can handle arrays of primitive types and objects.
#### Example
```java
package com.eazybytes.main;

import java.util.Arrays;

public class ToStringDemo {

    public static void main(String[] args) {
        int[] numbers = {1,2,3,4,5};
        System.out.println(Arrays.toString(numbers));
        System.out.println(numbers);// Output : [1,2,3,4,5]
    }

}
```
## Sorting Arrays
`Arrays.sort()` is a method provided by the `java.util.Arrays` class in Java, used for sorting arrays of primitive data types and objects. It sorts the specified array into ascending numerical or lexicographical order. This method uses the dual-pivot quicksort algorithm for sorting primitive types and the merge sort algorithm for sorting objects.
#### Example
```java
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        int[] numbers = {5, 2, 8, 4, 1};
        
        // Sort the entire array
        Arrays.sort(numbers);
        System.out.println("Sorted array: " + Arrays.toString(numbers));// [1,2,4,5,8]
    }
}

```
## Arrays.fill()
The `Arrays.fill()` method from the `java.util` package fills the specified array with the specified value.
#### Example
```java
package com.eazybytes.main;

import java.util.Arrays;

public class FillDemo {

    public static void main(String[] args) {

        int[] scores = new int[10];
        Arrays.fill(scores, 100);
        System.out.println(Arrays.toString(scores));

        int[] indices = new int[5];
        Arrays.setAll(indices, i -> i*2);
        System.out.println(Arrays.toString(indices));
        
    }

}
```
## Arrays.setAll()
In Java, the `Arrays.setAll()` method is used to set each element of an array to the result of applying a specified generator function to its index.
### Syntax
```java
public static void setAll(T[] array, IntFunction<? extends T> generator)
```
- **array :** the array whose elements are to be set.
- **generator :** a function that accepts an integer index and produces a value to be stored at that index in the array.
#### Example
Suppose we have an array of integers and we want to initialize it with consecutive even numbers starting from 0.
```java
import java.util.Arrays;
import java.util.function.IntFunction;

public class Main {
    public static void main(String[] args) {
        int size = 5;
        int[] arr = new int[size];
        
        Arrays.setAll(arr, index -> index * 2);
        
        // Output the array
        System.out.println(Arrays.toString(arr)); // Output: [0, 2, 4, 6, 8]
    }
}
```
In this example:
- We create an array of size 5.
- We use `Arrays.setAll()` to set each element of the array to `index * 2`, effectively assigning consecutive even numbers starting from 0.
- Finally, we print out the contents of the array.
### Notes
- The generator function is called for each index of the array in ascending order.
- It's important to ensure that the generator function does not throw any exceptions when called.
- The method throws `NullPointerException` if the specified array or generator is null.
## 2D Arrays
A 2D array, also known as a matrix, is a grid of elements where each element is identified by two indices - row and column. In Java, 2D arrays are used to represent matrices, tables, grids, or other 2-dimensional structures.
```java
// Declare and initialize a 2D array with specified dimensions
int[][] matrix = new int[rows][columns];

// Initialize a 2D array with predefined values
int[][] matrix = {{1, 2, 3},{4, 5, 6},{7, 8, 9}};
```
### Accessing Elements
Accessing elements in a 2D array involves specifying both row and column indices
```java
// Accessing an element at row i and column j
int element = matrix[i][j];
```
### Traversing a 2D Array
Traversing a 2D array requires nested loops to iterate through each row and column.
```java
for (int i = 0; i < matrix.length; i++) {
    for (int j = 0; j < matrix[i].length; j++) {
        // Accessing and performing operations on matrix[i][j]
    }
}
```
### Common Operations
- Transpose: Switching rows with columns in a 2D array.
- Matrix Addition: Adding two matrices of the same dimensions.
- Matrix Multiplication: Multiplying two matrices following specific rules.
## Matrix Addition
This Java program demonstrates how to add two matrices of the same dimensions.


















