---
layout: notes
title: "📓6.4: Array Algorithms" 
parent: "6️⃣ Arrays"
nav_order: 4
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 6.4](https://runestone.academy/ns/books/published/csawesome/Unit6-Arrays/topic-6-4-array-algorithms.html?mode=browsing) 

---

## Array Algorithms (FRQs)

In this lesson, you will study different Free Response Questions and responses that develop algorithms using arrays.


Here are some common **algorithms** that you should be familiar with for the AP CSA exam:

- 🔍 **Searching Algorithms:**
  - Determine the _minimum_ value in an array
  - Determine the _maximum_ value in an array
  - Search for a _specific element_ in the array
- ➕ **Acculumator Patterns:**
  - Compute a _sum_ of array elements
  - Compute an _average_ of array elements
  - Determine the _number of elements_ meeting specific _criteria_
- 🧪 **Testing Properties:**
  - Determine if _at least one element_ has a particular _property_
  - Determine if _all elements_ have a particular _property_
  - Determine the presence (or absence) of _duplicate_ elements
- ↔️ **Manipulating Array Order:**
  - _Shift/Rotate_ elements to the left or right
    > Requires keeping track of the current **INDEX**!
  - _Reverse_ the order of the elements
    > Requires keeping track of the current **INDEX**!

<div class="imp" markdown="block">
  
🔁 Here are two common **array traversal loops** that can be used for these algorithms:

  ```java
  for (int value : array) {
      if (value ....) {
          ...
      }
  }
  ```
  > **Enhanced for** (for-each) loops visit _EVERY ITEM_!
  ```java
  for (int i=0; i < array.length; i++) {
      if (array[i] ....) {
         ...
      }
  }
  ```
  > **Standard for** loops offer more flexibility, and keep track of the _INDEX_.

</div>

#### 💻 In-Class Activity: 
{:.no_toc}


<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit6-Arrays/topic-6-4-array-algorithms.html?mode=browsing"><button type="button" name="button" class="btn">CSAwesome Topic 6.4</button></a> 
2. Make sure you **SIGN IN**!
3. Complete all **Coding Exercises** in groups.

</div>


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
