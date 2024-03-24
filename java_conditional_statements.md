
# Conditional Statements and Looping Constructs

Conditional statements and looping constructs are fundamental control structures in Java that allow you to make decisions and iterate over sequences of statements based on certain conditions. Let's explore each of these concepts:

## Conditional Statements

Conditional statements allow you to execute different blocks of code based on whether a specified condition evaluates to true or false. In Java, there are mainly three types of conditional statements:

### 1. `if` Statement

The `if` statement is used to execute a block of code if the specified condition is true. It can be followed by an optional `else` block to execute a different block of code if the condition is false.

```java
int num = 10;

if (num > 0) {
    System.out.println("Positive number");
} else {
    System.out.println("Non-positive number");
}
```

### 2. `else-if` Statement

The `else-if` statement allows you to test multiple conditions sequentially. It is used when you have more than two possible outcomes.

```java
int num = 0;

if (num > 0) {
    System.out.println("Positive number");
} else if (num < 0) {
    System.out.println("Negative number");
} else {
    System.out.println("Zero");
}
```

### 3. `switch` Statement

The `switch` statement is used to select one of many code blocks to be executed based on the value of a variable or expression.

```java
int day = 3;
String dayName;

switch (day) {
    case 1:
        dayName = "Monday";
        break;
    case 2:
        dayName = "Tuesday";
        break;
    // Other cases...
    default:
        dayName = "Invalid day";
        break;
}

System.out.println("Day: " + dayName);
```

## Looping Constructs

Looping constructs allow you to execute a block of code repeatedly as long as a specified condition is true or for a fixed number of times. In Java, there are mainly three types of looping constructs:

### 1. `for` Loop

The `for` loop is used to iterate over a range of values or elements in an array. It consists of three parts: initialization, condition, and iteration.

```java
for (int i = 0; i < 5; i++) {
    System.out.println("Iteration: " + i);
}
```

### 2. `while` Loop

The `while` loop is used to repeatedly execute a block of code as long as the specified condition is true.

```java
int count = 0;

while (count < 5) {
    System.out.println("Count: " + count);
    count++;
}
```

### 3. `do-while` Loop

The `do-while` loop is similar to the `while` loop, but the condition is evaluated after the execution of the loop body, so the loop is guaranteed to execute at least once.

```java
int count = 0;

do {
    System.out.println("Count: " + count);
    count++;
} while (count < 5);
```

Understanding conditional statements and looping constructs is essential for controlling the flow of execution in Java programs. By utilizing these constructs effectively, you can implement complex logic and iterate over data structures efficiently.
