# Java Sorting Algorithms

**Author:** Dinidu Sachintha  
**Date:** 2024-05-15

## Abstract

This document provides a detailed study of key sorting algorithms in Java, covering Selection Sort, Bubble Sort, Insertion Sort, Merge Sort, Heap Sort, Tree Sort, and Counting Sort. It includes comprehensive algorithm descriptions, pseudocode, Java implementations, and analyses of their advantages and disadvantages. The comparison of these algorithms is based on their performance metrics and use cases, offering insights into both comparison-based and non-comparison-based sorting techniques.

## Table of Contents

1. [Introduction](#introduction)
    - [Background: Importance of Sorting in Computer Science](#background-importance-of-sorting-in-computer-science)
    - [Objectives: Purpose of the Document](#objectives-purpose-of-the-document)
2. [Sorting Algorithms Overview](#sorting-algorithms-overview)
    - [Classification](#classification)
    - [Comparison-Based Sorting Algorithms](#comparison-based-sorting-algorithms)
    - [Non-Comparison-Based Sorting Algorithms](#non-comparison-based-sorting-algorithms)
3. [Comparison-Based Sorting Algorithms](#comparison-based-sorting-algorithms-1)
    - [Bubble Sort](#bubble-sort)
        - [How does Bubble Sort Work without programming?](#how-does-bubble-sort-work-without-programming)
        - [Practical Scenario](#practical-scenario)
        - [Implementation of Bubble Sort](#implementation-of-bubble-sort)
        - [Advantages of Bubble Sort](#advantages-of-bubble-sort)
        - [Disadvantages of Bubble Sort](#disadvantages-of-bubble-sort)
        - [Where is the Bubble sort algorithm used?](#where-is-the-bubble-sort-algorithm-used)
    - [Selection Sort](#selection-sort)
        - [How does Selection Sort Work without programming?](#how-does-selection-sort-work-without-programming)
        - [Practical Scenario](#practical-scenario-1)
        - [Implementation of Selection Sort](#implementation-of-selection-sort)
        - [Advantages of Selection Sort Algorithm](#advantages-of-selection-sort-algorithm)
        - [Disadvantages of the Selection Sort Algorithm](#disadvantages-of-the-selection-sort-algorithm)
        - [Where is the Selection sort algorithm used?](#where-is-the-selection-sort-algorithm-used)

## Introduction

### Background: Importance of Sorting in Computer Science

Sorting is a fundamental operation in computer science, serving as a critical process in various applications such as searching, data analysis, and optimization. Efficient sorting algorithms improve the performance of other algorithms that require sorted data, such as binary search algorithms and merge operations. Sorting is essential for simplifying data processing and enhancing data presentation and storage. Understanding and implementing sorting algorithms is a core component of computer science education and practice.

### Objectives: Purpose of the Document

This document aims to provide a comprehensive study of several key sorting algorithms implemented in Java. By examining both comparison-based and non-comparison-based sorting algorithms, this document seeks to:
- Offer detailed explanations of each algorithm, including their theoretical foundations and practical implementations in Java.
- Analyze the time and space complexities of these algorithms to understand their efficiency.
- Discuss the advantages and disadvantages of each algorithm to highlight their appropriate use cases.

## Sorting Algorithms Overview

Sorting algorithms arrange elements of a list or array in a specific order (ascending or descending). Sorting is crucial in many applications, such as database management, data processing, and scientific computing. It is often a prerequisite for other algorithms, such as searching and merging, which require data to be in a sorted order for efficient operation.

### Classification

Sorting algorithms can be broadly classified into two categories: comparison-based sorting algorithms and non-comparison-based sorting algorithms.

### Comparison-Based Sorting Algorithms

Comparison-based sorting algorithms work by comparing elements to determine their relative order. These algorithms have a lower bound time complexity of O(n log n) in the average case, where n is the number of elements to be sorted. Some examples include:
- **Selection Sort**: This algorithm divides the input list into two parts: a sorted sublist and an unsorted sublist. It repeatedly finds the minimum element from the unsorted sublist and swaps it with the leftmost unsorted element.
- **Bubble Sort**: This algorithm repeatedly swaps adjacent elements if they are in the wrong order, effectively "bubbling" the largest elements to the end of the list.
- **Insertion Sort**: This algorithm builds the final sorted array one item at a time by taking an element from the input and inserting it into its correct position in the already sorted sublist.
- **Merge Sort**: This is a divide-and-conquer algorithm that recursively divides the input array into two halves, sorts them, and then merges the sorted halves.
- **Heap Sort**: This algorithm builds a binary heap data structure from the input array and then repeatedly extracts the maximum element from the heap to construct the sorted array.
- **Quick Sort**: This is another divide-and-conquer algorithm that selects a "pivot" element from the array and partitions the other elements into two sub-arrays, according to whether they are less than or greater than the pivot.

### Non-Comparison-Based Sorting Algorithms

Non-comparison-based sorting algorithms do not rely on comparisons between elements. Instead, they use the internal character of the values to be sorted. It can only be applied to some particular cases and requires specific values. Examples include:
- **Counting Sort**: This algorithm counts the number of occurrences of each distinct element and uses this information to construct the sorted array.
- **Radix Sort**: This algorithm sorts elements by processing individual digits or groups of digits, starting from the least significant digit or group.

## Comparison-Based Sorting Algorithms

### Bubble Sort

Bubble Sort is a simple sorting algorithm that repeatedly swaps adjacent elements if they are in the wrong order. It is an in-place algorithm with a time complexity of O(n^2), making it inefficient for large datasets.

#### How does Bubble Sort Work without programming?

Imagine you have a list of numbers that you want to sort, for example: [5, 3, 8, 4, 2]

**First Pass:**
- Compare the first two numbers (5 and 3). Since 5 is greater than 3, swap them. The list now looks like: [3, 5, 8, 4, 2].
- Move to the next pair (5 and 8). Since 5 is less than 8, no swap is needed.
- Move to the next pair (8 and 4). Since 8 is greater than 4, swap them. The list now looks like: [3, 5, 4, 8, 2]
- Move to the next pair (8 and 2). Since 8 is greater than 2, swap them. The list now looks like: [3, 5, 4, 2, 8].
- At the end of the first pass, the largest number (8) has "bubbled up" to its correct position at the end of the list.

  ![Bubble sort](https://github.com/Dinidu21/Sorting-Algorithms-Java-with-Implementation/blob/main/Bubble%20Sort/Untitled-2024-05-15-1525.png)

**Second Pass:**
- Start again at the beginning of the list.
- Compare the first two numbers (3 and 5). Since 3 is less than 5, no swap is needed.
- Move to the next pair (5 and 4). Since 5 is greater than 4, swap them. The list now looks like: [3, 4, 5, 2, 8].
- Move to the next pair (5 and 2). Since 5 is greater than 2, swap them. The list now looks like: [3, 4, 2, 5, 8].
- The second largest number (5) is now in its correct position, and the list is partially sorted.

![Bubble sort](https://github.com/Dinidu21/Sorting-Algorithms-Java-with-Implementation/blob/main/Bubble%20Sort/Untitled-2024-05-15-1525(1).png)

**Third Pass:**
- Start again at the beginning.
- Compare the first two numbers (3 and 4). Since 3 is less than 4, no swap is needed.
- Move to the next pair (4 and 2). Since 4 is greater than 2, swap them. The list now looks like: [3, 2, 4, 5, 8].
- The third largest number (4) is now in its correct position.

![Bubble sort](https://github.com/Dinidu21/Sorting-Algorithms-Java-with-Implementation/blob/main/Bubble%20Sort/Untitled-2024-05-15-1525(2).png)

**Fourth Pass:**
- Start again at the beginning.
- Compare the first two numbers (3 and 2). Since 3 is greater than 2, swap them. The list now looks like: [2, 3, 4, 5, 8].
- Now, all elements are in their correct positions.

![Bubble sort](https://github.com/Dinidu21/Sorting-Algorithms-Java-with-Implementation/blob/main/Bubble%20Sort/Untitled-2024-05-15-1525(3).png)


**Final Check:**
- The algorithm performs one more pass to check that no swaps are needed, confirming that the list is sorted.

![Bubble sort](https://github.com/Dinidu21/Sorting-Algorithms-Java-with-Implementation/blob/main/Bubble%20Sort/Untitled-2024-05-15-1525(4).png)


**Visual Example:**
- Initial list: [5, 3, 8, 4, 2]
- After 1st pass: [3, 5, 4, 2, 8]
- After 2nd pass: [3, 4, 2, 5, 8]
- After 3rd pass: [3, 2, 4, 5, 8]
- After 4th pass: [2, 3, 4, 5, 8]
- Final list (after check pass): [2, 3, 4, 5, 8]
  
#### Practical Scenario

Imagine you have a queue of people waiting for a movie and want to sort them alphabetically by their last name. You can use Bubble Sort like this:
1. Compare the last names of the first two people in line. If the second person's name comes alphabetically after the first,

 swap them.
2. Move to the next pair of people and repeat the comparison and possible swap.
3. Continue this process until you've gone through the entire line without needing to make any swaps, indicating the list is sorted.

#### Implementation of Bubble Sort

![Bubble sort](https://github.com/Dinidu21/Sorting-Algorithms-Java-with-Implementation/blob/main/Bubble%20Sort/codeimage-snippet_15.png)


```java
public class BubbleSort {
    public static void bubbleSort(int[] arr) {
        int n = arr.length;
        boolean swapped;
        for (int i = 0; i < n - 1; i++) {
            swapped = false;
            for (int j = 0; j < n - 1 - i; j++) {
                if (arr[j] > arr[j + 1]) {
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                    swapped = true;
                }
            }
            if (!swapped) break;
        }
    }
    
    public static void main(String[] args) {
        int[] arr = {5, 1, 4, 2, 8};
        bubbleSort(arr);
        System.out.println("Sorted array: ");
        for (int num : arr) {
            System.out.print(num + " ");
        }
    }
}
```

#### Advantages of Bubble Sort

- Simple to understand and implement.
- Requires only a few lines of code.
- Does not require additional memory allocation (in-place sorting).

#### Disadvantages of Bubble Sort

- Inefficient for large datasets due to its O(n^2) time complexity.
- Not suitable for applications requiring fast sorting.

#### Where is the Bubble sort algorithm used?

- Bubble sort is primarily used for educational purposes to help students understand the basic principles of sorting algorithms.
- In practice, it may be used in simple scenarios with small datasets where performance is not a critical factor.
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### Selection Sort

Selection Sort is a simple comparison-based sorting algorithm. It works by repeatedly finding the minimum element from the unsorted part of the array and moving it to the beginning.

#### How does Selection Sort Work without programming?

Imagine you have a list of numbers that you want to sort, for example: [29, 10, 14, 37, 13]

**First Pass:**
- Find the minimum element from the list [29, 10, 14, 37, 13]. The minimum is 10.
- Swap the minimum element (10) with the first element (29). The list now looks like: [10, 29, 14, 37, 13].

[!Selection Sort](https://github.com/Dinidu21/Sorting-Algorithms-Java-with-Implementation/blob/main/Selection%20Sort/Untitled-2024-05-15-1525.png)

**Second Pass:**
- Find the minimum element from the remaining unsorted list [29, 14, 37, 13]. The minimum is 13.
- Swap the minimum element (13) with the second element (29). The list now looks like: [10, 13, 14, 37, 29].

[!Selection Sort](https://github.com/Dinidu21/Sorting-Algorithms-Java-with-Implementation/blob/main/Selection%20Sort/Untitled-2024-05-15-1525(1).png)

**Third Pass:**
- Find the minimum element from the remaining unsorted list [14, 37, 29]. The minimum is 14.
- Swap the minimum element (14) with the third element (14). No change as it’s already in place. The list remains: [10, 13, 14, 37, 29].

[!Selection Sort](https://github.com/Dinidu21/Sorting-Algorithms-Java-with-Implementation/blob/main/Selection%20Sort/Untitled-2024-05-15-1525(2).png)

**Fourth Pass:**
- Find the minimum element from the remaining unsorted list [37, 29]. The minimum is 29.
- Swap the minimum element (29) with the fourth element (37). The list now looks like: [10, 13, 14, 29, 37].

[!Selection Sort](https://github.com/Dinidu21/Sorting-Algorithms-Java-with-Implementation/blob/main/Selection%20Sort/Untitled-2024-05-15-1525(3).png)

**Final Check:**
- The list is now sorted: [10, 13, 14, 29, 37].

[!Selection Sort](https://github.com/Dinidu21/Sorting-Algorithms-Java-with-Implementation/blob/main/Selection%20Sort/Untitled-2024-05-15-1525(4).png)

#### Practical Scenario

Consider you have a list of students' names and you want to sort them alphabetically. Selection Sort can be used to sort the names:
1. Look through the entire list of names to find the first name alphabetically and move it to the beginning.
2. Then look through the remaining list to find the next name and move it to the second position.
3. Continue this process until the entire list is sorted.

#### Implementation of Selection Sort

[!Selection Sort](https://github.com/Dinidu21/Sorting-Algorithms-Java-with-Implementation/blob/main/Selection%20Sort/codeimage-snippet_15.png)

```java
public class SelectionSort {
    public static void selectionSort(int[] arr) {
        int n = arr.length;
        
        for (int i = 0; i < n - 1; i++) {
            // Find the minimum element in unsorted array
            int minIndex = i;
            for (int j = i + 1; j < n; j++) {
                if (arr[j] < arr[minIndex]) {
                    minIndex = j;
                }
            }
            // Swap the found minimum element with the first element
            int temp = arr[minIndex];
            arr[minIndex] = arr[i];
            arr[i] = temp;
        }
    }
    
    public static void main(String[] args) {
        int[] arr = {29, 10, 14, 37, 13};
        selectionSort(arr);
        System.out.println("Sorted array: ");
        for (int num : arr) {
            System.out.print(num + " ");
        }
    }
}
```

#### Advantages of Selection Sort Algorithm

- Simple to understand and implement.
- Performs well on small lists.
- Requires O(1) extra space (in-place sorting).

#### Disadvantages of the Selection Sort Algorithm

- Inefficient for large lists due to its O(n^2) time complexity.
- Does not adapt to the data (performance is the same regardless of the order of the elements).

#### Where is the Selection sort algorithm used?

- Selection Sort is often used for educational purposes to demonstrate the concept of sorting algorithms.
- It can be useful for small datasets or when memory space is limited and in-place sorting is required.

---

