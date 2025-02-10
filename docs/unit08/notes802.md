---
layout: notes
title: "📓8.2: Traversing 2D Arrays" 
parent: "8️⃣ 2D Arrays"
nav_order: 2
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 8.2](https://runestone.academy/ns/books/published/csawesome/Unit8-2DArray/topic-8-2-2D-array-loops.html?mode=browsing) 

---

## Traversing 2D Arrays with Nested Loops

Since 2D arrays are really arrays of arrays you can also use a _nested_ **enhanced for-each loop** to loop through all elements in an array. We loop through each of the inner arrays and loop through all the values in each inner array. Notice the type of the outer loop array variable - it is an array that will hold each row, `String[]` in the example below for a 2D String array. The `type` of the variables in the for-each loops must match the type of the array. For-each loops are much simpler since you don't have to use the indices and the `[]`'s, but you can only use them if you are not going to change the values in an array of primitive types since the variable val below will not change the original array.

```java
String[][] data;
// Nested For-Each loops to traverse a 2D String array
for (String[] row : data) {
  for (String col : row) {
    System.out.println(col);
  }
}
```
> In this case the ``for (String[] row : array)`` means to loop through each element of the _outer_ array (`data`) which will set the current ``row`` to the current array of columns. Then you can loop through the values (`col`) in the column array.

### 2D Array Algorithms

All of the array **algorithms** can be applied to 2D arrays too. For example, 🧮 **counting** and 🔍 **searching** algorithms work very similarly. 

#### Counting
{:.no_toc}

What will the following code print out? Can you complete the  method called ``getTotalForCol`` that gets the total for a column? To do this, you must loop through the rows. The array's length will tell you how many rows you have since it is an array of arrays, while the length of the array's first element will tell you how many columns.
  
```java
public static int getTotalForRow(int row, int[][] a)
       {
           int total = 0;
           for (int col = 0; col < a[0].length; col++)
           {
               total = total + a[row][col];
           }
           return total;
       }

       // Complete the method getTotalForCol below
       public static int getTotalForCol(int col, int[][] a)
       {
           int total = 0;
           // Add a loop here to total a column col

           return total;
       }

       public static void main(String[] args)
       {
           int[][] matrix = { {1, 2, 3}, {4, 5, 6}};
           System.out.println(getTotalForRow(0, matrix));
           System.out.println(getTotalForCol(0, matrix));
       }
```

#### Iterate through a Subset
{:.no_toc}

You can loop through a smaller part of a 2D array as long as you use a **standard for loop**. You can change the starting value and ending value to loop through a subset of a 2D array.

```java
       public static int countValues(int value, int[][] a, int rowStart, 
                                  int rowEnd, int colStart, int colEnd)
       {
           int count = 0;
           for (int row = rowStart; row <= rowEnd; row++)
           {
               for (int col = colStart; col <= colEnd; col++)
               {
                   if (a[row][col] == value)
                   {
                        count++;
                   }
               }
           }
           return count;
       }

       public static void main(String[] args)
       {
           int[][] matrix = { {3, 2, 3}, {4, 3, 6}, {8, 9, 3}, {10, 3, 3}};
           System.out.println(countValues(3, matrix, 0, 2, 0, 2));
       }
```

#### Linear Search
{:.no_toc}

What will the following code print? Can you change the code to work for a String 2D array instead of an int array? Note that the indices row and col will still be ints.

```java
       public static boolean search(int[][] array, int value)
       {
           boolean found = false;
           for (int row = 0; row < array.length; row++)
           {
               for (int col = 0; col < array[0].length; col++)
               {
                   if (array[row][col] == value)
                   {
                        found = true;
                   }
               }
           }
           return found;
       }

       public static void main(String[] args)
       {
           int[][] matrix = { {3, 2, 3}, {4, 3, 6}, {8, 9, 3}, {10, 3, 3}};
           System.out.println(search(matrix, 10));
           System.out.println(search(matrix, 11));

           // Comment out the code above, and try these:
           // String[][] matrix2 = { {"a","b","c"},{"d","e","f"} };
           // System.out.println(search(matrix2, "b"));

       }
```


#### 2D Arrays Game
{:.no_toc}

<div class="task" markdown="block">

🎲 Try the game below to practice! Click on **Arrays** and then check on **2D** and click on the elements of the `*` array that would be printed out by the given code. If you're stuck, check on `Labels` to see the indices. We encourage you to work in pairs and see how high a score you can get.

</div>

<iframe height="700px" width="100%" style="margin-left:10%;max-width:80%" src="https://csa-games.netlify.app/"></iframe>

---

## ⭐️ Summary 

- We can iterate through 2D arrays using **nested standard for loops** or **nested enhanced for-each loops**.

- The _outer_ loop for a 2D array usually traverses the **rows**, while the _inner_ loop traverses the **columns** in a single row.

- The 2D array's `length` gives the _number of rows_. A row's length `array[0].length` gives the _number of columns_.

- Nested iteration statements can be written to traverse the 2D array in "row-major order" or "column-major order."

- In an enhanced for each loop, the variable of the outer loop must be the type of each row, which is a 1D array. The inner enhanced for loop variable must be the same type as the elements stored in the array.

- All standard 1D array algorithms can be applied to 2D array objects.

- When applying sequential/linear search algorithms to 2D arrays, each row must be accessed then sequential/linear search applied to each row of a 2D array.


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
