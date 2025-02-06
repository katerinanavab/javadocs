---
layout: notes
title: "📓7.5: Searching Algorithms" 
parent: "7️⃣ ArrayLists"
nav_order: 5
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 7.5](https://runestone.academy/ns/books/published/csawesome/Unit7-ArrayList/topic-7-5-searching.html?mode=browsing) 

---

## Searching Algorithms

Computers store vast amounts of data. One of the strengths of computers is their ability to find data _quickly_. This ability is called **searching**. 

For the AP CSA exam you will need to know both **linear (sequential) search** and **binary search** algorithms.

* 🔍➡️ **Sequential/Linear search** typically starts at the _first_ element in an array or ArrayList and looks through _all_ the items one by one until it either:
  * Finds the desired value and then returns the `index` where the value was found. 
  * Or if it searches the entire array or list _without_ finding the value, it returns `-1` (which is an **invalid** index).
* 🔍↔️ **Binary search** can only be used on data that has been _SORTED_ or stored in order. It checks the _middle_ of the data to see if that middle value is less than, equal, or greater than the desired value and then based on the results of that it narrows the search.
  * It cuts the search space in half each time!

<iframe width="560" height="315" src="https://www.youtube.com/embed/DHLCXXX1OtE?si=O1JJVpGGdjhtsnS7" title="YouTube video player" frameborder="0" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

> If **binary search** requires the values in an array or list to be *sorted*, how can you do that?  There are many **sorting algorithms** which are covered in the next lesson.


### Sequential/Linear Search

🔍➡️ **Sequential** or **linear** search can be used to find a value in *unsorted* data. It usually starts at the _first_ element and walks through the array or list until it finds the value it is looking for and returns its `index`. 

If it reaches the end of the array or list _without finding_ the value, the search method usually returns a `-1` to show that it didn't find the value in the array or list. 

#### Array
{:.no_toc}

```java
/**
 * Finds the index of a value in an array of integers.
 * @param elements an array containing the items to be searched.
 * @param target the item to be found in elements.
 * @return an index of target in elements if found; -1 otherwise.
*/
public static int sequentialSearch(int[] elements, int target) {
    for (int j = 0; j < elements.length; j++) {
        if (elements[j] == target) {
            return j;
        }
    }
    return -1;
}
```

{:.highlight} 
Many of our examples will use arrays for simplicity since with arrays, we know _how many items_ we have and the _size won't change_ during runtime. 

> There are methods such as ``contains`` that can be used in ArrayLists instead of writing your own algorithms. However, they are not in the AP CSA Java subset.

Below is the same search with an ``ArrayList`` **data structure** instead. The same algorithms can be used with arrays or ``ArrayList``s, but notice that ``size()`` and ``get(i)`` are used with ``ArrayList``s instead of ``length`` and ``[i]`` which are used in arrays. 

#### ArrayList
{:.no_toc}

```java
/**
 * Finds the index of a value in an ArrayList of integers.
 * @param elements an array containing the items to be searched.
 * @param target the item to be found in elements.
 * @return an index of target in elements if found; -1 otherwise.
*/
public static int sequentialSearch(ArrayList<Integer> elements, int target) {
    for (int j = 0; j < elements.size(); j++) {
        if (elements.get(j) == target) {
            return j;
        }
    }
    return -1;
}
```

### Binary Search

🔍↔️ How do you search for something in a phone book or dictionary that is in alphabetical or numerical order? If you're looking for something beginning with M or on page 100 in a 200 page book, you wouldn't want to start with page 1. You would probably start looking somewhere in the middle of the book. This is the idea behind **binary search**.

If your array or list is already in order (sorted), binary search will on average find an element or determine that it is missing much more quickly than a linear search. But binary search can only be used if the data is sorted.

Binary search keeps dividing the sorted search space into half. It compares a target value to the value in the middle of a range of indices.  If the value isn't found it looks again in either the left or right half of the current range. Each time through the loop it eliminates half the values in the search area until either the value is found or there is no more data to look at.  See the animation below from [AlvaroIsrael on Github](https://github.com/AlvaroIsrael/binary-search):

![image](Figures/binary-search-small.gif)

Binary search calculates the middle index as ``left + right / 2`` where left starts out at 0 and right starts out at the array length - 1 (the index of the last element). Remember that integer division gives an integer result so 2.5 becomes 2. It compares the value at the middle index with the target value (the value you are searching for).  If the target value is less than the value at the middle it sets right to middle minus one. If the target value is greater than the value at the middle it sets left to middle plus one. Otherwise the values match and it returns the middle index. It also stops when left is greater than right which indicates that the value wasn't found and it returns -1.

The code for an _iterative_ ``binarySearch`` below is from the AP CSA course description: 

```java
public static int binarySearch(int[] elements, int target) {
    int left = 0;
    int right = elements.length - 1;
    while (left <= right) {
        int middle = (left + right) / 2;
        if (target < elements[middle]) {
            right = middle - 1;
        }
        else if (target > elements[middle]) {
            left = middle + 1;
        }
        else {
            return middle;
        }
    }
    return -1;
}
```
> A _recursive_ version of this algorithm will be covered in Unit 10.

You can also use binary search with a ``String`` array.  But, when you look for a ``String``, be sure to use ``compareTo`` method rather than ``<`` or ``>`` which can only be used with primitive types.  Remember how the ``String`` method ``compareTo`` works:

   -  **int compareTo(String other)** returns a negative value if the current string is less than the ``other`` string, 0 if they have the same characters in the same order, and a positive value if the current string is greater than the ``other`` string.

```java
public static int binarySearch(String[] elements, String target) {
    int left = 0;
    int right = elements.length - 1;
    while (left <= right) {
        int middle = (left + right) / 2;
        if (target.compareTo(elements[middle]) < 0) {
            right = middle - 1;
        }
        else if (target.compareTo(elements[middle]) > 0) {
            left = middle + 1;
        }
        else {
            return middle;
        }
    }
    return -1;
}
```

### Runtimes

How do we choose between two algorithms that solve the same problem? They usually have different characteristics and **runtimes** which measures how fast they run. For the searching problem, it depends on your data.

Binary search is much faster than linear search, especially on large data sets, but it can only be used on sorted data. Often with runtimes, computer scientist think about the **worst case behavior**. With searching, the worst case is usually if you cannot find the item. With linear search, you would have to go through the whole array before realizing that it is not there, but binary search is much faster even in this case because it eliminates half the data set in each step. We can measure an informal runtime by just counting the number of steps.

Here is a table that compares the worst case runtime of each search algorithm given an array of n elements. The runtime here is measured as the number of times the loop runs in each algorithm or the number of elements we need to check in the worst case when we don't find the item we are looking for. Notice that with linear search, the worst case runtime is the size of the array n, because it has to look through the whole array. For the binary search runtime, we can calculate the number of times you can divide n in half until you get to 1. So, for example 8 elements can be divided in half to narrow down to 4 elements, which can be further divided in half to narrow down to 2 elements, which can be further divided in half to get down to 1 element, and then if that is wrong, to 0 elements, so that is 4 divisions or guesses to get the answer (8->4->2->1->0). In the table below, every time we double the size of N, we need at most one more guess or comparison with binary search. It's much faster than linear search!

N | Linear Search | Binary Search
--- | -------- | ------- |
2 | 2 comparisons | 2 comparisons
4 | 4             | 3
8 | 8            | 4
16 | 16          | 5
100 | 100         | 7

Runtimes can be described with mathematical functions. For an array of size n, linear search runtime is a linear function, and binary search runtime is a function of log base 2 of n (or log n + 1 comparisons). This is called the big-O runtime function in computer science, for example O(log n) vs. O(n). You can compare the growth of functions like n and log\ :sub:`2`\ n as n, the data size, grows and see that binary search runs much faster for any n.  You don't need to know the log n runtime growth function for the AP exam, but you should be able to calculate how many steps binary search takes for a given n by counting how many times you can divide it in half. Or you can start at 1 and keep a count of how many times you can double it with the powers of two (1, 2, 4, 8, 16, 32, 64, 128, 256, 512, 1024, etc.) until you reach a number that is slightly above n.

#### 💻 In-Class Activity: Search Runtimes
{:.no_toc}

<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit7-ArrayList/topic-7-5-searching.html?mode=browsing"><button type="button" name="button" class="btn">CSAwesome Topic 7.5</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: Search Runtimes** in groups.

</div>

---

## ⭐️ Summary

- There are standard algorithms for **searching**:
  - **Sequential/linear search** algorithms check each element in order until the desired value is found or all elements in the array or ArrayList have been checked.
  - The **binary search** algorithm starts at the _middle_ of a sorted array or ArrayList and eliminates half of the array or ArrayList in each iteration until the desired value is found or all elements have been eliminated.

- Data must be in **sorted** order to use the binary search algorithm. This algorithm will be covered more in Unit 10.

- Informal **run-time** comparisons of program code segments can be made using statement execution counts.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
