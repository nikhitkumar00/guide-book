
# Data Structures and Algorithms

## Array Class

In Java, the `Array` class provides static methods for dynamically creating and manipulating arrays. It is part of the `java.util` package.

### Creating Arrays

```java
int[] numbers = new int[5]; // Creating an array of integers with size 5
String[] names = {"Alice", "Bob", "Charlie"}; // Creating an array of strings with initialization
```

### Accessing Elements

```java
int[] numbers = {10, 20, 30, 40, 50};
int firstNumber = numbers[0]; // Accessing the first element
int lastNumber = numbers[numbers.length - 1]; // Accessing the last element
```

### Array Methods

The `Array` class provides various utility methods for working with arrays, such as sorting, searching, and copying.

```java
int[] numbers = {5, 3, 8, 2, 7};
Arrays.sort(numbers); // Sorting the array
int index = Arrays.binarySearch(numbers, 8); // Binary search for element 8
int[] copy = Arrays.copyOf(numbers, numbers.length); // Copying the array
```

## Strings

In Java, the `String` class represents sequences of characters. Strings are immutable, meaning their values cannot be changed after creation.

### Creating Strings

```java
String str1 = "Hello"; // Using string literal
String str2 = new String("World"); // Using constructor
```

### String Methods

The `String` class provides numerous methods for manipulating strings, such as concatenation, substring, length, and case conversion.

```java
String str = "Hello, World!";
int length = str.length(); // Getting the length of the string
String substring = str.substring(7); // Getting substring starting from index 7
String upperCase = str.toUpperCase(); // Converting the string to uppercase
```

### String Comparison

Strings can be compared using the `equals()` method for content comparison or the `==` operator for reference comparison.

```java
String str1 = "hello";
String str2 = "hello";
boolean isEqual = str1.equals(str2); // Content comparison
boolean isSameReference = (str1 == str2); // Reference comparison
```
