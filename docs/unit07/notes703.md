---
layout: notes
title: "📓7.3: ArrayLists & Loops" 
parent: "7️⃣ ArrayLists"
nav_order: 3
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 7.3](https://runestone.academy/ns/books/published/csawesome/Unit7-ArrayList/topic-7-3-arraylist-loops.html?mode=browsing) 

---

## Traversing ArrayLists with Loops

🔁 ``ArrayList``s can be **traversed** with ``while`` loops and both standard and
enhanced ``for`` loops much the same way we use those constructs to loop over an
array.

### Enhanced For-Each Loop

You can use a enhanced ``for`` loop to traverse _all of the items_ in an
``ArrayList``, just like you do with an array when you only care about the
**values** in the list and **not their indices**. 

An example is shown below:

```java
ArrayList<Integer> myList = new ArrayList<Integer>();
myList.add(50);
myList.add(30);
myList.add(20);
int total = 0;
for (Integer value : myList) {
  total += value;
}
System.out.println("Sum of all elements: " + total);
```
> 💬 **DISCUSS:** What does the following code do? Guess before you run it. Then, add another enhanced for each loop that _computes the product_ of all the elements in myList by multiplying them. Print out the product after the new loop.

Note however that you CANNOT use the enhanced ``for`` loop if you want to **add** or **remove** elements while traversing an ``ArrayList``. If an ``ArrayList`` is modified, such as by calling the ``add`` or ``remove`` methods, while it is being looped over, it will cause the loop to throw a ``ConcurrentModificationException``. If you need to modify an ``ArrayList`` while looping over it, you’ll need to use a regular ``while`` or ``for`` loop.

<div class="warn" markdown="block">

**Enhanced for-each** loops are often convenient but CANNOT be used in all situations! Only use for-each loops when you want to loop through *all* the values in an `ArrayList`, in _sequential_ order, _without making changes_.
  
- 🚫 Do not use for-each loops if you need to **modify values** in the list.
- 🚫 Do not use for-each loops if you need to keep track of the current **index**.
- 🚫 Do not use for-each loops for non-sequential traversals (like iterating through only part of a list, or in a different order).

</div>

### Standard For Loop

### While Loop

---

## ⭐️ Summary



---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
