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
Use the enhanced for each loop with arrays whenever you can, because it _cuts down on errors_. You can use it whenever you need to **loop through all the elements** of an array, and don't need to know their index and don't need to change their values. It starts with the first item in the array (the one at index `0`) and continues through in order to the last item in the array. 

See the examples below in Java that loop through an `int` and a `String` array. Notice the type of the loop variable is the type of the array.

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

Try the following code. Notice the for each loop with an int array and a String array. Add another high score and another name to the arrays and run again.

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
