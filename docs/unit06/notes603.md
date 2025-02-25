---
layout: notes
title: "📓6.3: Arrays & For-Each Loops" 
parent: "6️⃣ Arrays"
nav_order: 3
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 6.3](https://runestone.academy/ns/books/published/csawesome/Unit6-Arrays/topic-6-3-arrays-with-foreach.html?mode=browsing) 

---

## Traversing Arrays with For-Each Loops

There is a special kind of loop that can be used with arrays that is called an **enhanced for loop** or a **for-each loop**. This loop is much easier to write because it _does not involve an index variable_ or the use of the `[]`. It just sets up a variable that is set to each **value** in the array successively. This type of loop can only be used with arrays and some other collections of items like ArrayLists which we will see in the next unit.

To set up a for-each loop, use `for (type variable : arrayname)` where the type is the type for elements in the array, and read it as "_for each variable value in arrayname_". 

{:.highlight}
Use the enhanced for-each loop with arrays whenever you can, because it _cuts down on errors_! You can use it whenever you need to **loop through all the elements** of an array, don't need to know their **index**, and don't need to **change** their values. It automatically starts by "visiting" the first item in the array (the one at index `0`) and continues through, _in order_, to the last item in the array. 

See the examples below in Java that loop through both an `int` and a `String` array:

```java
  int[] highScores = { 10, 9, 8, 8};
  String[] names = {"Jamal", "Emily", "Destiny", "Mateo"};

  // for each loop: for each value in highScores
  // for (type variable : arrayname)
  for (int value : highScores) {
      // Notice no index or [ ], just the variable value!
      System.out.println( value );
  }
  // for each loop with a String array to print each name
  // the type for variable name is String!
  for (String name : names) {
      System.out.println( name );
  }
```
> Add another high score and another name to the arrays and run again!

### For-Each Loop Limitations

What if we had a loop that _incremented_ all the elements in the array. Would that work with an enhanced for-each loop? Unfortunately not! 

Because only the **temporary variable** in the loop changes, _not the real array values_. We would need an **indexed** loop to modify array elements. Try this code in the [Java Visualizer](http://www.pythontutor.com/visualize.html#code=%20%20%20public%20class%20IncrementLoop%0A%20%20%20%7B%20%20%20%20%20%20%0A%20%20%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%0A%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20int%5B%20%5D%20values%20%3D%20%7B6,%202,%201,%207,%2012,%205%7D%3B%0A%20%20%20%20%20%20%20%20//%20Can%20this%20loop%20increment%20the%20values%3F%0A%20%20%20%20%20%20%20%20for%20%28int%20val%20%3A%20values%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20val%2B%2B%3B%0A%20%20%20%20%20%20%20%20%20%20System.out.println%28%22New%20val%3A%20%22%20%2B%20val%29%3B%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20//%20Print%20out%20array%20to%20see%20if%20they%20really%20changed%0A%20%20%20%20%20%20%20%20for%20%28int%20v%20%3A%20values%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20System.out.print%28v%20%2B%20%22%20%22%29%3B%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%7D%0A%20%20%20%7D%0A%20%20%20&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false&curInstr=0) and step through the code to see why it doesn't work.

<div class="warn" markdown="block">

**Enhanced for-each** loops CANNOT be used in all situations! Only use for-each loops when you want to loop through *all* the values in an array, _without changing_ their values.
  
- 🚫 Do not use for-each loops if you need to keep track of the **index**.
- 🚫 Do not use for-each loops if  you need to **change values** in the array.
- 🚫 Do not use for-each loops if you want to loop through only part of an array or in a different order.

</div>


#### 💻 In-Class Activity: 
{:.no_toc}


<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit6-Arrays/topic-6-3-arrays-with-foreach.html?mode=browsing"><button type="button" name="button" class="btn">CSAwesome Topic 6.3</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: SpellChecker 2** activity in pairs.

</div>

---

## ⭐️ Summary

- An **enhanced for loop**, also called a **for-each loop**, can be used to loop through an array _without using an index variable_.

- An enhanced for loop header includes a variable, referred to as the enhanced for loop variable, that holds each value in the array.

- For each iteration of the enhanced for loop, the enhanced for loop variable is assigned a copy of an element without using its index.

- Assigning a new value to the enhanced for loop variable does not change the value stored in the array.

- Program code written using an enhanced for loop to traverse and access elements in an array can be rewritten using an indexed for loop or a while loop.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
