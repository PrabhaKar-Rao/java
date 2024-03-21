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





