---
layout: notes
title: "📓6.2: Arrays & For Loops" 
parent: "6️⃣ Arrays"
nav_order: 2
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 6.2](https://runestone.academy/ns/books/published/csawesome/Unit6-Arrays/topic-6-2-traversing-arrays.html?mode=browsing) 

---

## Traversing Arrays with For Loops

### Index Variables

In the last lesson, we mentioned that you can use a variable for the index of an array. You can even do math with that index and have an arithmetic expression inside the [], like below.

```java
  // highScores array declaration
  int[] highScores = { 10, 9, 8, 8};
  // use a variable for the index
  int index = 3;
  // modify array value at index
  highScores[index] = 11;
  // print array value at index
  System.out.println(  highScores[index] );
  System.out.println(  highScores[index - 1] );
```
> 💬 **DISCUSS:** What does the code above print out? You can follow the code in this <a href="http://www.pythontutor.com/visualize.html#code=public%20class%20ArrayWithIndexVar%20%7B%0A%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%20%7B%0A%20%20%20%20%20%20//%20highScores%20array%20declaration%0A%20%20%20%20%20%20int%5B%5D%20highScores%20%3D%20%7B%2010,%209,%208,%208%7D%3B%0A%20%20%20%20%20%20//%20use%20a%20variable%20for%20the%20index%0A%20%20%20%20%20%20int%20index%20%3D%203%3B%0A%20%20%20%20%20%20//%20modify%20array%20value%20at%20index%0A%20%20%20%20%20%20highScores%5Bindex%5D%20%3D%2011%3B%0A%20%20%20%20%20%20//%20print%20array%20value%20at%20index%0A%20%20%20%20%20%20System.out.println%28%20%20highScores%5Bindex%5D%20%29%3B%0A%20%20%20%20%20%20System.out.println%28%20%20highScores%5Bindex%20-%201%5D%20%29%3B%0A%20%20%20%20%7D%0A%7D&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false" target="_blank"  style="text-decoration:underline"> Java Visualizer</a> and look at the image depicting the array below.

![image](Figures/arraywithindex.png)

<div class="task" markdown="block">

What do you think the following code will print out? First trace through it on paper keeping track of the array and the index variable. Then, run it to see if you were right. You can also follow it in the <a href="http://www.pythontutor.com/visualize.html#code=%20public%20class%20Test1%0A%20%20%20%7B%0A%20%20%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%0A%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20String%5B%20%5D%20names%20%3D%20%7B%22Jamal%22,%20%22Emily%22,%20%22Destiny%22,%20%22Mateo%22,%20%22Sofia%22%7D%3B%20%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20int%20index%20%3D%201%3B%0A%20%20%20%20%20%20%20%20System.out.println%28names%5Bindex%20-%201%5D%29%3B%0A%20%20%20%20%20%20%20%20index%2B%2B%3B%0A%20%20%20%20%20%20%20%20System.out.println%28names%5Bindex%5D%29%3B%0A%20%20%20%20%20%20%20%20System.out.println%28names%5Bindex/2%5D%29%3B%0A%20%20%20%20%20%20%20%20names%5Bindex%5D%20%3D%20%22Rafi%22%3B%0A%20%20%20%20%20%20%20%20index--%3B%0A%20%20%20%20%20%20%20%20System.out.println%28names%5Bindex%2B1%5D%29%3B%0A%20%20%20%20%20%20%7D%0A%20%20%20%7D%0A%20%20%20&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false" target="_blank"  style="text-decoration:underline">Java Visualizer</a>.

```java
String[] names = {"Jamal", "Emily", "Destiny", "Mateo", "Sofia"};

int index = 1;
System.out.println(names[index - 1]);
index++;
System.out.println(names[index]);
System.out.println(names[index / 2]);
names[index] = "Rafi";
index--;
System.out.println(names[index + 1]);
```

</div>

### For Loop to Traverse Arrays

We can use iteration with a standard **for loop** to "visit" each element of an array.  This is called **traversing** the array. Just start the index at **0** and loop while the index is less than the **length** of the array. 

{:.highlight}
Note that the variable **i** (short for _index_) is often used in loops as the **loop counter variable** and is used here to access each element of an array with its index (position).

![image](Figures/arrayForLoop.png)

For example, here is a loop traversing the ``highScores`` array to print every score. Follow the code below in the <a href="http://www.pythontutor.com/visualize.html#code=public%20class%20ArrayLoop%0A%7B%0A%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%20%0A%20%20%20%20%7B%0A%0A%20%20%20%20%20%20%20%20int%5B%5D%20highScores%20%3D%20%7B%2010,%209,%208,%208%7D%3B%0A%20%20%20%20%20%20%20%20for%20%28int%20i%20%3D%200%3B%20i%20%3C%20highScores.length%3B%20i%2B%2B%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20System.out.println%28%20%20highScores%5Bi%5D%20%29%3B%0A%20%20%20%20%20%20%20%20%7D%20%0A%20%20%20%20%7D%0A%7D&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false" target="_blank"  style="text-decoration:underline">Java Visualizer</a>.

```java
  int[] highScores = { 10, 9, 8, 11};
  for (int i = 0; i < highScores.length; i++) {
      System.out.println(  highScores[i] );
  }
```

{:.highlight} 
Using a variable as the index is a powerful **data abstraction** feature because it allows us to use loops with arrays where the loop counter variable is the index of the array! This allows our code to generalize to work for the whole array.

<div class="task" markdown="block">

What do you think the following code will print out? First trace through it on paper keeping track of the array and the index variable. Then, run it to see if you were right. 

```java
String[] names = {"Jamal", "Emily", "Destiny", "Mateo", "Sofia"};

for (int i = 0; i < names.length; i++) {
  System.out.println(names[i]);
}
```

> Try adding your name and a friend's name to the array names and run the code again. Did the code work without changing the loop?

</div>

### Modifying Values in an Array

The following code demonstrates a loop that changes the values in an array. In this code, the array is passed as an **argument** to the static methods in the class. You can try the code in the <a href="http://www.pythontutor.com/visualize.html#code=public%20class%20ArrayLoop%0A%20%20%20%7B%0A%0A%20%20%20%20%20//%20What%20does%20this%20method%20do%3F%0A%20%20%20%20%20%20public%20static%20void%20multAll%28int%5B%5D%20values,%20int%20amt%29%0A%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20for%20%28int%20i%20%3D%200%3B%20i%20%3C%20values.length%3B%20i%2B%2B%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20values%5Bi%5D%20%3D%20values%5Bi%5D%20*%20amt%3B%0A%20%20%20%20%20%20%20%20%7D%20%0A%20%20%20%20%20%20%7D%20%0A%20%20%20%20%20%20%0A%20%20%20%20%20%20//%20What%20does%20this%20method%20do%3F%0A%20%20%20%20%20%20public%20static%20void%20printValues%28int%5B%5D%20values%29%0A%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20for%20%28int%20i%20%3D%200%3B%20i%20%3C%20values.length%3B%20i%2B%2B%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20System.out.println%28%20%20values%5Bi%5D%20%29%3B%0A%20%20%20%20%20%20%20%20%7D%20%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%0A%20%20%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%0A%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20int%5B%5D%20numArray%20%3D%20%20%7B2,%206,%207,%2012,%205%7D%3B%0A%20%20%20%20%20%20%20%20multAll%28numArray,%202%29%3B%0A%20%20%20%20%20%20%20%20printValues%28numArray%29%3B%0A%20%20%20%20%20%20%7D%0A%20%20%20%7D%0A%20%20%20%20%20%20&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false" target="_blank"  style="text-decoration:underline">Java Visualizer</a>.

```java
public static void multAll(int[] values, int amt) {
  for (int i = 0; i < values.length; i++) {
    values[i] = values[i] * amt;
  }
}

public static void printValues(int[] values) {
  for (int i = 0; i < values.length; i++) {
    System.out.println(values[i]);
  }
}

public static void main(String[] args) {
  int[] numArray = {2, 6, 7, 12, 5};
  multAll(numArray, 2);
  printValues(numArray);
}
```
> 💬 **DISCUSS:** What do these methods do? Trace through it, keeping track of the array values and the output.

{:highlight} 
Arrays in Java are **objects**, so the array variables are references to an address in memory. When an array is passed as an argument to a method, the **name** of the array refers to its **address** in memory. Therefore, any changes to the array in the method _will affect the original array_. 
> Since arrays can be very large, we do not want to copy them entirely when we pass them into methods.

### Looping Backwards

⬅️ You don't have to loop through an array from the front to the back, you can loop by starting at the **final index** of the array and move toward the front during each time through the loop. 

In the example below, the method ``getIndexOfLastSmallerItem`` returns the index of the last element in the array that is smaller than the given argument (the "target"). 

```java
public static int getIndexOfLastSmallerItem(int[] values, int target) {

  for (int index = values.length - 1; index >= 0; index--) {
    if (values[index] < target) {
      return index;
    }
  }
  return -1;
}
```

> The **return** statement inside the loop **stops** the execution of the loop and the method and returns the index that is found immediately back to the main method. It returns `-1` if there is no number in the array that is smaller than the given number.

<div class="task" markdown="block">

Can you add another method that finds the index of the last element **greater** than the target, instead of smaller, and have your `main` method print out a test of it? 
  
Call this method `getIndexOfLastGreaterItem` and give it 2 **arguments** and a **return** value like the method above.

</div>

### Looping through Part of an Array

You don't always have to loop through _all_ of the elements of an array!  You can loop through just some of the elements of an array using a for loop.  The following code doubles the first five elements in an array.  Notice that it uses a complex conditional (``&&``) on line 14 to make sure that the loop doesn't go beyond the length of the array, because if you had an array that had less than 5 elements, you wouldn't want the code to try to double the 5th element which doesn't exist! Notice that in this code, the array is a private instance variable of the class ArrayWorker. It is created in the constructor and changed or accessed by the methods.

### Common Errors When Looping Through an Array
{:.no_toc}

When processing all array elements, be careful to start at the first index which is ``0`` and end at the last index. Usually loops are written so that the index starts at 0 and continues while the index is less than ``arrayName.length`` since (``arrayName.length - 1``) is the index for the last element in the array. Make sure you do not use ``<=`` instead of ``<``! If the index is less than 0 or greater than (``arrayName.length - 1``), an **ArrayIndexOutOfBoundsException** will be  thrown.  **Off by one** errors, where you go off the array by 1 element, are easy to make when traversing an array which result in an **ArrayIndexOutOfBoundsException** being thrown.


#### 💻 In-Class Activity: SpellChecker
{:.no_toc}

<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit6-Arrays/topic-6-2-traversing-arrays.html?mode=browsing"><button type="button" name="button" class="btn">CSAwesome Topic 6.2</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: SpellChecker** activity in pairs.

</div>

#### 🎲 Practice Game: Loops with Arrays
{:.no_toc}

Try the game below to practice! Click on **Arrays** and click on the element of the `*` array that would be printed out by the given code. If you're stuck, check on Labels to see the indices. We encourage you to work in pairs and see how high a score you can get.

<html>
        <iframe height="700px" width="100%" style="margin-left:10%;max-width:80%" src="https://csa-games.netlify.app/"></iframe>
    <script>      window.scrollTo(0, 0);</script>
</html>


---

## ⭐️ Summary

- Iteration (loops) can be used to access all the elements in an array, **traversing the array**.

- Traversing an array with an indexed for loop or while loop requires elements to be accessed using their indices.

- Since the index for an array starts at 0 and end at the number of elements − 1, "off by one" errors are easy to make when traversing an array, resulting in an **ArrayIndexOutOfBoundsException** being thrown.


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
