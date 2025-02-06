---
layout: notes
title: "📓7.6: Sorting Algorithms" 
parent: "7️⃣ ArrayLists"
nav_order: 6
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 7.6](https://runestone.academy/ns/books/published/csawesome/Unit7-ArrayList/topic-7-6-sorting.html?mode=browsing) 

---

## Sorting Algorithms

There are many sorting algorithms to put an array or ArrayList elements in alphabetic or numerical order. We will show these algorithms below for arrays. The three sorting algorithms that you need to know for the AP CSA exam are:

* **Selection Sort** - Select the smallest item from the current location on to the end of the array and swap it with the value at the current position.  Do this from index 0 to the array length - 2.  You don't have to process the last element in the array, it will already be sorted when you compare the prior element to the last element.
* **Insertion Sort** - Insert the next unsorted element in the already sorted part of the array by moving larger values to the right.  Start at index 1 and loop through the entire array.
* **Merge Sort** - Break the elements into two parts and recursively sort each part.  An array of one item is sorted (base case).  Then merge the two sorted arrays into one.
  > MergeSort will be covered in Unit 10.

### Selection Sort

The selection sort that you need to know for the exam starts at index 0 and looks through the entire array keeping track of the the index of the smallest value in the array and then swaps the value at the smallest index with the value at index 0.  Then it does the same thing for index 1, then 2, and so on until it reaches the length of the array minus one.  At this point the array is sorted in ascending order.

<iframe width="560" height="315" src="https://www.youtube.com/embed/g-PGLbMth_g?si=N_YyodtHasxVEsF8" title="YouTube video player" frameborder="0" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

👯 Here is a folk dance video that demonstrates the selection sort process:

<iframe width="560" height="315" src="https://www.youtube.com/embed/Ns4TPTC8whw?si=LaJ1QeBRrH5ecawu" title="YouTube video player" frameborder="0" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

To identify a selection sort look for the following:

* a nested for loop with the outer loop starting at 0 and ending when the index reaches length - 1 (see line 7 below)
* the index of the smallest value should start at the outer loop index (see line 9 below)
* the inner loop should start at the outer loop index + 1 and loop through the whole array (see line 10 below)

* if the value in the array at the index of the inner loop is less than the value at the smallest index then set the smallest index to the index of the inner loop (see lines 12 - 15)
* swap the value at the outer loop index and the smallest value (the one at the smallest value index) (see lines 17-19)

The code for ``selectionSort`` below is from the AP CSA course description:

```java
public static void selectionSort(int[] elements)
      {
          for (int j = 0; j < elements.length - 1; j++)
          {
              int minIndex = j;
              for (int k = j + 1; k < elements.length; k++)
              {
                  if (elements[k] < elements[minIndex])
                  {
                      minIndex = k;
                  }
              }
              int temp = elements[j];
              elements[j] = elements[minIndex];
              elements[minIndex] = temp;
          }
      }
```

### Insertion Sort

The insertion sort that you need to know for the exam starts at index 1 and inserts the value at index 1 into its correct place in the already sorted part (the part to the left of the current index). It moves any value larger than the value stored in temp to the right until it either finds the appropriate place to put temp or gets to the front of the array.

<iframe width="560" height="315" src="https://www.youtube.com/embed/JU767SDMDvA?si=CD9wJ7AnHo65a3RF" title="YouTube video player" frameborder="0" allow="accelerometer;  clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

👯 Here is a folk dance video that demonstrates the insertion sort process:

<iframe width="560" height="315" src="https://www.youtube.com/embed/ROalU379l3U?si=dyUVAag8YDyD_Wbk" title="YouTube video player" frameborder="0" allow="accelerometer;  clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

To identify an insertion sort look for the following:

* an outer for loop that starts at 1 and loops through the entire array (see line 7)
* storing the element value at the outer loop index in temp (see line 9)
* setting the possible index to the outer loop index (see line 10)
* an inner while loop that loops while the possible index is greater than 0 and the value in temp is less than the value at the possible index minus one (see line 11)
* set the value at the possible index to the one to the left of it (the one at possible index minus one) (see line 13)
* decrement the possible index (subtract one from it) (see line 14)
* when the while loop ends set the value at the possible index to temp (see line 16)

The code for ``insertionSort`` below is from the AP CSA course description:

```java
      public static void insertionSort(int[] elements)
      {
          for (int j = 1; j < elements.length; j++)
          {
              int temp = elements[j];
              int possibleIndex = j;
              while (possibleIndex > 0 && temp < elements[possibleIndex - 1])
              {
                  elements[possibleIndex] = elements[possibleIndex - 1];
                  possibleIndex--;
              }
              elements[possibleIndex] = temp;
          }
      }
```

#### 💻 In-Class Activity: Sort Runtimes
{:.no_toc}

<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit7-ArrayList/topic-7-6-sorting.html?mode=browsing"><button type="button" name="button" class="btn">CSAwesome Topic 7.6</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: Sort Runtimes** in groups.

</div>

---

## ⭐️ Summary

- **Selection sort** and **insertion sort** are _iterative_ sorting algorithms that can be used to sort elements in an array or ArrayList.

- Informal **run-time** comparisons of program code segments can be made using statement execution counts.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
