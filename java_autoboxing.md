
# Autoboxing and Unboxing

Autoboxing and unboxing are features introduced in Java 5 to automatically convert between primitive types and their corresponding wrapper classes. These features help simplify code and make it more readable by reducing the need for manual conversions between primitives and their wrapper classes.

## Autoboxing

Autoboxing is the automatic conversion of a primitive type to its corresponding wrapper class when an object of that class is required. Autoboxing is performed implicitly by the Java compiler.

```java
// Autoboxing example
int num = 10;
Integer numObj = num; // Autoboxing int to Integer
```

In the above example, the primitive `int` value `10` is automatically converted to an `Integer` object when assigning it to the `numObj` variable.

## Unboxing

Unboxing is the automatic conversion of a wrapper class object to its corresponding primitive type when a primitive type is required. Unboxing is also performed implicitly by the Java compiler.

```java
// Unboxing example
Integer numObj = 20;
int num = numObj; // Unboxing Integer to int
```

In this example, the `Integer` object `20` is automatically converted to a primitive `int` value when assigning it to the `num` variable.

## Autoboxing and Unboxing with Collections

Autoboxing and unboxing are commonly used in conjunction with collections, such as `ArrayList`, `HashMap`, etc., which require objects rather than primitives.

```java
// Autoboxing and unboxing with ArrayList
ArrayList<Integer> numbers = new ArrayList<>();
numbers.add(10); // Autoboxing int to Integer
int firstNumber = numbers.get(0); // Unboxing Integer to int
```

In this example, the `add()` method of `ArrayList` automatically converts the `int` value `10` to an `Integer` object, and the `get()` method returns an `Integer` object that is automatically converted back to a primitive `int` value.

## Performance Considerations

While autoboxing and unboxing provide convenience, they may incur a slight performance overhead due to the creation of additional objects and the associated memory allocation. In performance-critical code sections, manual conversion between primitives and their wrapper classes may be preferred to optimize performance.

## Best Practices

-   Use autoboxing and unboxing judiciously, especially in performance-sensitive code.
-   Be aware of potential `NullPointerException` when unboxing `null` wrapper objects.
-   Consider using primitive types directly when dealing with performance-critical code sections.

Autoboxing and unboxing are convenient features in Java that help simplify code by automatically converting between primitives and their corresponding wrapper classes. While they provide convenience, developers should be mindful of performance implications and use them judiciously, especially in performance-critical sections of code.
