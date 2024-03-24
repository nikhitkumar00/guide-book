
# Java Collection Framework: Generics

Generics in Java allow you to create classes, interfaces, and methods that can work with any data type. They provide type safety by allowing you to specify the type of data that a class or method can work with, without sacrificing flexibility.

## Declaration

Generics are declared using angle brackets (`<>`) and type parameters.

```java
public class Box<T> {
    private T value;

    public T getValue() {
        return value;
    }

    public void setValue(T value) {
        this.value = value;
    }
}
```

In this example, `T` is a type parameter that represents any reference type. You can use any valid Java identifier as a type parameter.

## Using Generics

When you instantiate a generic class, you specify the actual type that the type parameter will represent.

```java
Box<Integer> integerBox = new Box<>();
integerBox.setValue(10);
int value = integerBox.getValue(); // No casting required
```

In this example, `T` is replaced with `Integer` when creating an instance of the `Box` class. This ensures type safety and eliminates the need for explicit casting when retrieving the value.

## Generic Methods

You can also create generic methods that can work with any data type.

```java
public class Util {
    public static <T> T getLastElement(T[] array) {
        if (array == null || array.length == 0) {
            return null;
        }
        return array[array.length - 1];
    }
}
```

In this example, the method `getLastElement` has a type parameter `T`. It can accept an array of any type and return the last element of the array.

```java
Integer[] numbers = {1, 2, 3, 4, 5};
Integer lastNumber = Util.getLastElement(numbers);
```

## Wildcards

Wildcards (`?`) allow you to work with unknown types. They are useful when you want to write code that is independent of the actual type.

```java
public void printList(List<?> list) {
    for (Object obj : list) {
        System.out.println(obj);
    }
}
```

In this example, `List<?>` means a list of unknown type. You can pass a list of any type to this method.

Generics provide type safety and code reusability in Java. They allow you to create classes, interfaces, and methods that can work with any data type, while ensuring type safety at compile time. Understanding generics is essential for writing flexible and maintainable Java code.

# Java Collection Framework: Collection

In Java, the `Collection` interface is the root interface of the Java Collection Framework. It represents a group of objects, known as elements, and provides a common set of methods for working with collections. Let's explore the properties of the `Collection` interface:

## Properties of Collection

1. **Size**: The `size()` method returns the number of elements in the collection.

    ```java
    Collection<String> collection = new ArrayList<>();
    int size = collection.size(); // Returns the number of elements
    ```

2. **Addition**: The `add()` method adds a single element to the collection. It returns `true` if the collection changed as a result of the call.

    ```java
    Collection<String> collection = new ArrayList<>();
    boolean added = collection.add("Java"); // Adds element "Java" to the collection
    ```

3. **Removal**: The `remove()` method removes a single instance of the specified element from the collection, if it is present. It returns `true` if an element was removed as a result of the call.

    ```java
    Collection<String> collection = new ArrayList<>();
    collection.add("Java");
    boolean removed = collection.remove("Java"); // Removes element "Java" from the collection
    ```

4. **Containment**: The `contains()` method returns `true` if the collection contains the specified element.

    ```java
    Collection<String> collection = new ArrayList<>();
    collection.add("Java");
    boolean contains = collection.contains("Java"); // Returns true
    ```

5. **Iteration**: The `iterator()` method returns an iterator over the elements in the collection, allowing sequential access to each element.

    ```java
    Collection<String> collection = new ArrayList<>();
    collection.add("Java");
    Iterator<String> iterator = collection.iterator();
    while (iterator.hasNext()) {
        String element = iterator.next();
        System.out.println(element);
    }
    ```

The `Collection` interface provides a unified interface for working with collections of objects in Java. It defines methods for adding, removing, and querying elements, as well as iterating over the elements of the collection. Understanding the properties of the `Collection` interface is essential for effectively working with collections in Java.

# Java Collection Framework: Linked List

In Java, a linked list is a data structure that consists of a sequence of elements, where each element points to the next element in the sequence. Java provides the `LinkedList` class that implements the `List` interface and represents a doubly-linked list.

## Creating a Linked List

You can create a linked list by instantiating the `LinkedList` class.

```java
import java.util.LinkedList;

LinkedList<String> linkedList = new LinkedList<>();
```

## Adding Elements

You can add elements to the linked list using the `add()` method.

```java
linkedList.add("Apple");
linkedList.add("Banana");
linkedList.add("Orange");
```

## Accessing Elements

You can access elements in the linked list using methods like `get()` and iterators.

```java
String first = linkedList.getFirst();
String last = linkedList.getLast();
```

## Removing Elements

You can remove elements from the linked list using methods like `remove()`.

```java
linkedList.remove("Banana");
```

## Enumerations

Enumerations in Java provide a way to iterate over a collection of objects. The `Enumeration` interface is part of the legacy collection framework and is used with legacy classes like `Vector` and `Hashtable`.

```java
import java.util.Enumeration;
import java.util.Vector;

Vector<String> vector = new Vector<>();
vector.add("One");
vector.add("Two");
vector.add("Three");

Enumeration<String> enumeration = vector.elements();
while (enumeration.hasMoreElements()) {
    String element = enumeration.nextElement();
    System.out.println(element);
}
```

## Set and Uniqueness in Set

A set is a collection that does not allow duplicate elements. Java provides several implementations of the `Set` interface, such as `HashSet`, `LinkedHashSet`, and `TreeSet`.

```java
import java.util.Set;
import java.util.HashSet;

Set<String> set = new HashSet<>();
set.add("Apple");
set.add("Banana");
set.add("Apple"); // Duplicate element, will not be added

System.out.println(set); // Output: [Apple, Banana]
```

Using sets ensures uniqueness of elements, as duplicate elements are automatically removed. This property makes sets useful for tasks where uniqueness is required, such as maintaining a collection of unique values.
