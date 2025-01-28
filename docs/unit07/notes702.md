---
layout: notes
title: "📓7.2: ArrayList Methods" 
parent: "7️⃣ ArrayLists"
nav_order: 2
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 7.2](https://runestone.academy/ns/books/published/csawesome/Unit7-ArrayList/topic-7-2-arraylist-methods.html?mode=browsing) 

---

## ArrayList Methods

The following are the ``ArrayList`` methods that you need to know for the AP CSA exam. These are included on the <a href="https://apstudents.collegeboard.org/ap/pdf/ap-computer-science-a-java-quick-reference_0.pdf" target="_blank">AP CSA Java Quick Reference Sheet</a> that you will receive during the exam so you do not need to memorize them. 
> **NOTE:** The `E` in the method headers below stands for the type of the element in the ArrayList; this type `E` can be any Object type.

-  `int size()` returns the **number of elements** in the list

-  `boolean add(E obj)` **appends** obj to the *end* of the list, and also returns true

-  `void add(int index, E obj)` **inserts** obj at the index, moves any current objects at index or beyond to the _right_ (to a higher index), and also returns the replaced element

-  `E remove(int index)` **removes** the item at the index, shifts remaining items to the _left_ (to a lower index), and also returns the replaced element

-  `E get(int index)` returns the **item** in the list at the index

-  `E set(int index, E obj)` **replaces** the item at index with obj, and also returns the replaced element

### ``size()``

As we saw in the last lesson, you can get the number of items in a ``ArrayList``
using its ``size()`` method. The ``ArrayList`` starts out empty with a size
of 0.

```java
ArrayList<String> list = new ArrayList<String>();
System.out.println( list.size() );
```

{:.highlight}
With arrays, you use the ``length`` field to get the number of items in the array. But, with an ``ArrayList`` you use the ``size()`` method to get the number of items in the ``ArrayList``. The number of items in an empty ``ArrayList`` is 0.
> **AP EXAM NOTE:** You will not be penalized if you mix up ``length`` and ``size()`` in the CSA exam.

### ``add(obj)``

### ``add(index,obj)``

### ``remove(index)``

### ``get(index)`` and ``set(index, obj)``

### Comparing Arrays and ArrayLists




---

## ⭐️ Summary

-  `int size()` returns the **number of elements** in the list

-  `boolean add(E obj)` **appends** obj to the *end* of the list, and also returns true

-  `void add(int index, E obj)` **inserts** obj at the index, moves any current objects at index or beyond to the _right_ (to a higher index), and also returns the replaced element

-  `E remove(int index)` **removes** the item at the index, shifts remaining items to the _left_ (to a lower index), and also returns the replaced element

-  `E get(int index)` returns the **item** in the list at the index

-  `E set(int index, E obj)` **replaces** the item at index with obj, and also returns the replaced element


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
