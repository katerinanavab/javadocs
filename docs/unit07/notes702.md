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

As we saw in the last lesson, you can get the **number of items** in a ``ArrayList`` using its ``size()`` method. The ``ArrayList`` starts out empty with a size of 0.

```java
ArrayList<String> list = new ArrayList<String>();
System.out.println( list.size() );
```

{:.highlight}
With arrays, you use the ``length`` field to get the number of items in the array. But, with an ``ArrayList`` you use the ``size()`` method to get the number of items in the ``ArrayList``. The number of items in an empty ``ArrayList`` is 0.
> **AP EXAM NOTE:** You will not be penalized if you mix up ``length`` and ``size()`` in the CSA exam.

### ``add(obj)``

You can **add** values to an ``ArrayList`` using the method ``add(obj)``, which will add the object to the _end_ of the list, just like you would join the end of the line to board a bus.

<div class="task" markdown="block">

Try the code below to see how the list **changes** as each object is added to the end. 

```java
ArrayList<String> nameList = new ArrayList<String>();
nameList.add("Diego");
System.out.println(nameList);
nameList.add("Grace");
System.out.println(nameList);
System.out.println(nameList.size());
```
> Can you add your name to the list and then print out the list?

</div>

When adding Integers to a list, you can use the `Integer` object constructor like ``add(new Integer(5))``... but you can also just add the primitive `int` value directly, like ``add(5)``, and it will be changed into an ``Integer`` object automatically. 
> 📦 This is called **autoboxing**. When you pull an ``int`` value out of a list of ``Integers``, that is called **unboxing**.

{:.highlight}
You can put any kind of **objects** into an ``ArrayList``. Even instances of a class that you wrote! 

For example, here is an ``ArrayList`` of ``Creature``s:
```java
ArrayList<Creature> zoo = new ArrayList<Creature>();
zoo.add(new Creature("Bella", "Unicorn", 15));
zoo.add(new Creature("Bobby", "Bear", 8));
```

### ``add(index,obj)``

There are actually two different ``add`` methods in the ``ArrayList`` class:
1. The ``add(obj)`` method **adds** the passed object to the _end_ of the list.
2. The ``add(index,obj)`` method **inserts** the passed object at the passed `index`, but first _shifts over_ any existing values to higher indices to make room for the new object.

<div class="task" markdown="block">

💬 **DISCUSS:** What will the code below print out? Try figuring it out before running it.
> Remember that `ArrayList`s start at index 0 and that the `add(index,obj)` always takes the index as the first argument.

```java
ArrayList<Integer> list1 = new ArrayList<Integer>();
list1.add(1);
// adds the number 2 to the end of the list
list1.add(2);
// This will add the number 3 at index 1
list1.add(1, 3);
// This will add the number 4 at index 1
list1.add(1, 4);
System.out.println(list1);
System.out.println(list1.size());
```

</div>

### ``remove(index)``

You can also **remove** values from an ``ArrayList`` using the ``remove(index)`` method. It removes the item located at the specified _index_, which affects the underlying array in two ways: all of the other items after that index shift to a lower index, and the size of the ``ArrayList`` is decreased by 1.
> Note that this method is **NON-VOID**: It also _returns_ the item that was removed... in case you need to see it (but usually you don't).

<div class="task" markdown="block">

💬 **DISCUSS:** What will the code below print out? Try figuring it out before running it.

```java
ArrayList<Integer> list2 = new ArrayList<Integer>();
list2.add(1);
list2.add(2);
list2.add(3);
list2.remove(1);
System.out.println(list2);
```
> The ``remove(int index)`` method doesn't remove the object that matches the integer value given. In the example above it doesn't remove the value `1` – it removes the value `2` at **index** `1`.

</div>

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
