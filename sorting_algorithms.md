
# Sorting Algorithms

Sorting algorithms are used to rearrange a collection of items into a specific order. Here are three common sorting algorithms implemented in Java:

## Bubble Sort

Bubble sort repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order. The pass through the list is repeated until the list is sorted.

```java
public class BubbleSort {
    public static void bubbleSort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n-1; i++) {
            for (int j = 0; j < n-i-1; j++) {
                if (arr[j] > arr[j+1]) {
                    // Swap arr[j] and arr[j+1]
                    int temp = arr[j];
                    arr[j] = arr[j+1];
                    arr[j+1] = temp;
                }
            }
        }
    }
}
```

## Quick Sort

Quick sort is a divide-and-conquer algorithm. It picks an element as a pivot and partitions the given array around the pivot. It then recursively sorts the sub-arrays before and after the pivot.

```java
public class QuickSort {
    public static void quickSort(int[] arr, int low, int high) {
        if (low < high) {
            int pi = partition(arr, low, high);
            quickSort(arr, low, pi - 1);
            quickSort(arr, pi + 1, high);
        }
    }

    private static int partition(int[] arr, int low, int high) {
        int pivot = arr[high];
        int i = (low - 1);
        for (int j = low; j < high; j++) {
            if (arr[j] < pivot) {
                i++;
                // Swap arr[i] and arr[j]
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }
        // Swap arr[i+1] and arr[high] (or pivot)
        int temp = arr[i + 1];
        arr[i + 1] = arr[high];
        arr[high] = temp;
        return i + 1;
    }
}
```

## Merge Sort

Merge sort is another divide-and-conquer algorithm. It divides the input array into two halves, recursively sorts them, and then merges the sorted halves.

```java
public class MergeSort {
    public static void mergeSort(int[] arr, int l, int r) {
        if (l < r) {
            int m = (l + r) / 2;
            mergeSort(arr, l, m);
            mergeSort(arr, m + 1, r);
            merge(arr, l, m, r);
        }
    }

    private static void merge(int[] arr, int l, int m, int r) {
        int n1 = m - l + 1;
        int n2 = r - m;
        int[] L = new int[n1];
        int[] R = new int[n2];
        for (int i = 0; i < n1; ++i)
            L[i] = arr[l + i];
        for (int j = 0; j < n2; ++j)
            R[j] = arr[m + 1 + j];
        int i = 0, j = 0;
        int k = l;
        while (i < n1 && j < n2) {
            if (L[i] <= R[j]) {
                arr[k] = L[i];
                i++;
            } else {
                arr[k] = R[j];
                j++;
            }
            k++;
        }
        while (i < n1) {
            arr[k] = L[i];
            i++;
            k++;
        }
        while (j < n2) {
            arr[k] = R[j];
            j++;
            k++;
        }
    }
}
```

These sorting algorithms are fundamental to computer science and are used extensively in various applications. Understanding their implementations and complexities is essential for designing efficient algorithms and systems.

# Fundamental Data Structures

Data structures are fundamental building blocks used to organize and manage data efficiently. Here are two important data structures, along with their implementations and basic operations:

## Hash Tables

Hash tables are a data structure that stores key-value pairs. They use a hash function to compute an index into an array of buckets or slots, from which the desired value can be found.

### Implementation in Java

```java
import java.util.HashMap;

public class HashTableExample {
    public static void main(String[] args) {
        // Creating a hash table
        HashMap<String, Integer> hashMap = new HashMap<>();

        // Adding key-value pairs to the hash table
        hashMap.put("John", 25);
        hashMap.put("Alice", 30);
        hashMap.put("Bob", 20);

        // Accessing values using keys
        int johnsAge = hashMap.get("John");
        System.out.println("John's age: " + johnsAge);
    }
}
```

## Binary Search Trees (BST)

A binary search tree (BST) is a binary tree data structure in which each node has at most two child nodes (left and right), and the left child node contains a value less than or equal to the parent node, while the right child node contains a value greater than the parent node.

### Traversing BST

Traversing a BST means visiting each node in a specific order. There are three common ways to traverse a BST: in-order, pre-order, and post-order traversal.

#### In-order Traversal

In in-order traversal, nodes are visited in the following order: left, root, right.

```java
class TreeNode {
    int val;
    TreeNode left, right;

    public TreeNode(int val) {
        this.val = val;
        left = right = null;
    }
}

public class BinaryTree {
    public static void inOrderTraversal(TreeNode root) {
        if (root != null) {
            inOrderTraversal(root.left);
            System.out.print(root.val + " ");
            inOrderTraversal(root.right);
        }
    }
}
```

#### Pre-order Traversal

In pre-order traversal, nodes are visited in the following order: root, left, right.

```java
public class BinaryTree {
    public static void preOrderTraversal(TreeNode root) {
        if (root != null) {
            System.out.print(root.val + " ");
            preOrderTraversal(root.left);
            preOrderTraversal(root.right);
        }
    }
}
```

#### Post-order Traversal

In post-order traversal, nodes are visited in the following order: left, right, root.

```java
public class BinaryTree {
    public static void postOrderTraversal(TreeNode root) {
        if (root != null) {
            postOrderTraversal(root.left);
            postOrderTraversal(root.right);
            System.out.print(root.val + " ");
        }
    }
}
```

These data structures and their operations are fundamental to computer science and are used extensively in various applications. Understanding their implementations and characteristics is essential for designing efficient algorithms and systems.

# Greedy Algorithm

Greedy algorithms are algorithms that make locally optimal choices at each step with the hope of finding a global optimum solution. These algorithms are used in optimization problems where the objective is to find the best solution from a set of possible solutions.

Example of a Greedy Algorithm: The Knapsack Problem

```java
import java.util.Arrays;
import java.util.Comparator;

public class GreedyAlgorithm {

    public static void main(String[] args) {
        int[] values = {60, 100, 120};
        int[] weights = {10, 20, 30};
        int capacity = 50;
        System.out.println("Maximum value in the knapsack: " + knapsack(values, weights, capacity));
    }

    public static double knapsack(int[] values, int[] weights, int capacity) {
        int n = values.length;
        Item[] items = new Item[n];
        for (int i = 0; i < n; i++) {
            items[i] = new Item(values[i], weights[i]);
        }
        Arrays.sort(items, Comparator.comparingDouble(Item::valuePerUnitWeight).reversed());

        double totalValue = 0;
        for (Item item : items) {
            int currentWeight = item.getWeight();
            int currentValue = item.getValue();
            if (capacity - currentWeight >= 0) {
                capacity -= currentWeight;
                totalValue += currentValue;
            } else {
                double fraction = (double) capacity / currentWeight;
                totalValue += currentValue * fraction;
                break;
            }
        }
        return totalValue;
    }

    static class Item {
        private int value;
        private int weight;

        public Item(int value, int weight) {
            this.value = value;
            this.weight = weight;
        }

        public double valuePerUnitWeight() {
            return (double) value / weight;
        }

        public int getValue() {
            return value;
        }

        public int getWeight() {
            return weight;
        }
    }
}
```

# Divide and Conquer Algorithm

Divide and conquer is a problem-solving paradigm based on recursively breaking down a problem into sub-problems of the same or related type until they become simple enough to be solved directly. The solutions to the sub-problems are then combined to solve the original problem.

Example of a Divide and Conquer Algorithm: Merge Sort

```java
public class MergeSort {
    public static void mergeSort(int[] arr, int l, int r) {
        if (l < r) {
            int m = (l + r) / 2;
            mergeSort(arr, l, m);
            mergeSort(arr, m + 1, r);
            merge(arr, l, m, r);
        }
    }

    private static void merge(int[] arr, int l, int m, int r) {
        int n1 = m - l + 1;
        int n2 = r - m;
        int[] L = new int[n1];
        int[] R = new int[n2];
        for (int i = 0; i < n1; ++i)
            L[i] = arr[l + i];
        for (int j = 0; j < n2; ++j)
            R[j] = arr[m + 1 + j];
        int i = 0, j = 0;
        int k = l;
        while (i < n1 && j < n2) {
            if (L[i] <= R[j]) {
                arr[k] = L[i];
                i++;
            } else {
                arr[k] = R[j];
                j++;
            }
            k++;
        }
        while (i < n1) {
            arr[k] = L[i];
            i++;
            k++;
        }
        while (j < n2) {
            arr[k] = R[j];
            j++;
            k++;
        }
    }

    public static void main(String[] args) {
        int[] arr = {12, 11, 13, 5, 6, 7};
        System.out.println("Array before sorting:");
        printArray(arr);
        mergeSort(arr, 0, arr.length - 1);
        System.out.println("Array after sorting:");
        printArray(arr);
    }

    public static void printArray(int[] arr) {
        for (int i : arr) {
            System.out.print(i + " ");
        }
        System.out.println();
    }
}
```

# Dynamic Programming

Dynamic programming is a method for solving complex problems by breaking them down into simpler sub-problems. It stores the solutions to sub-problems in a table and reuses these solutions to avoid redundant computations.

Example of Dynamic Programming: Fibonacci Series

```java
public class Fibonacci {
    public static void main(String[] args) {
        int n = 10;
        System.out.println("Fibonacci series up to " + n + " terms:");
        for (int i = 0; i < n; i++) {
            System.out.print(fibonacci(i) + " ");
        }
    }

    public static int fibonacci(int n) {
        if (n <= 1) {
            return n;
        }
        int[] fib = new int[n + 1];
        fib[0] = 0;
        fib[1] = 1;
        for (int i = 2; i <= n; i++) {
            fib[i] = fib[i - 1] + fib[i - 2];
        }
        return fib[n];
    }
}
```

These algorithms are widely used in computer science and are essential for solving various optimization and computational problems. Understanding their implementations and characteristics is crucial for designing efficient algorithms and systems.

# String Algorithms

String algorithms are algorithms that operate on strings or sequences of characters. They are used in various applications such as text processing, pattern matching, and data compression. Here are three important string algorithms:

## Naive Search Algorithm

The naive search algorithm, also known as the brute-force or simple search algorithm, is a basic string searching algorithm that checks for occurrences of a pattern within a text by comparing each character of the pattern with each character of the text.

```java
public class NaiveSearch {
    public static void search(String text, String pattern) {
        int n = text.length();
        int m = pattern.length();

        for (int i = 0; i <= n - m; i++) {
            int j;
            for (j = 0; j < m; j++) {
                if (text.charAt(i + j) != pattern.charAt(j))
                    break;
            }
            if (j == m) {
                System.out.println("Pattern found at index " + i);
            }
        }
    }

    public static void main(String[] args) {
        String text = "ABABCABABABAABCABAB";
        String pattern = "ABAB";
        search(text, pattern);
    }
}
```

## Boyer-Moore String Searching Algorithm

The Boyer-Moore algorithm is an efficient string searching algorithm that performs comparisons based on the last occurrence of each character in the pattern. It skips characters in the text based on a precomputed table of character shifts.

```java
public class BoyerMoore {
    private static final int NO_OF_CHARS = 256;

    public static void search(String text, String pattern) {
        int n = text.length();
        int m = pattern.length();
        int[] badChar = new int[NO_OF_CHARS];

        badCharHeuristic(pattern, m, badChar);

        int s = 0; // s is shift of the pattern with respect to text
        while (s <= (n - m)) {
            int j = m - 1;

            // Keep reducing index j of pattern while characters of pattern and text are matching
            while (j >= 0 && pattern.charAt(j) == text.charAt(s + j))
                j--;

            // If the pattern is present at the current shift, then index j will become -1 after the above loop
            if (j < 0) {
                System.out.println("Pattern found at index " + s);
                s += (s + m < n) ? m - badChar[text.charAt(s + m)] : 1;
            } else {
                // Shift the pattern so that the bad character in text aligns with the last occurrence of it in pattern
                s += Math.max(1, j - badChar[text.charAt(s + j)]);
            }
        }
    }

    private static void badCharHeuristic(String str, int size, int[] badChar) {
        for (int i = 0; i < NO_OF_CHARS; i++)
            badChar[i] = -1;
        for (int i = 0; i < size; i++)
            badChar[(int) str.charAt(i)] = i;
    }

    public static void main(String[] args) {
        String text = "ABAAABCD";
        String pattern = "ABC";
        search(text, pattern);
    }
}
```

## Other String Matching Algorithms

Other string matching algorithms include the Rabin-Karp algorithm, Knuth-Morris-Pratt algorithm, and Aho-Corasick algorithm, among others. These algorithms offer different trade-offs in terms of time complexity, space complexity, and preprocessing requirements, depending on the specific characteristics of the problem and the input data.

These string algorithms are essential tools for text processing and pattern matching tasks. Understanding their implementations and characteristics is crucial for effectively solving string-related problems in various applications.
