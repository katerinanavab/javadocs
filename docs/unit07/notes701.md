---
layout: notes
title: "📓7.1: ArrayList Basics" 
parent: "7️⃣ ArrayLists"
nav_order: 1
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 7.1](https://runestone.academy/ns/books/published/csawesome/Unit7-ArrayList/topic-7-1-arraylist-basics.html?mode=browsing) 

#### Using a GitHub Template for class notes
{:.no_toc}

<div class="setup" markdown="block">

1. Go to the public template **repository** for our class: [BWL-CS Java Template](https://github.com/BWL-CS/java-template)
2. Click the <button type="button" name="button" class="btn btn-green">Use this template</button> button above the list of files then select `Create a new repository`
3. Specify the **repository name**: `CS2-Unit-7-Notes`
4. Click <button type="button" name="button" class="btn btn-green">Create repository</button>
    > Now you have **your own personal copy** of this starter code that you can always access under the `Your repositories` section of GitHub! 
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` and wait for the environment to load, _then you're ready to code_!
7. 📝 Take notes in this Codespace during class, coding along with the instructor.

</div>

---

## Intro to ArrayLists

In the last unit, we learned about using arrays to hold **collections** of related data. However arrays are not very _flexible_. Most notably, the size of an array is established at the time of creation and cannot be changed. What if you **don't know how big** the collection of data will be? What if you want to both **add** and **remove** items from a collection? 
> For example, if you wanted to represent a shopping list, you might _add to the list_ throughout the week and _remove things from the list_ while you are shopping. You probably would not know how many items will be on the list at the beginning of the week.

![image](Figures/lists.jpg)

{:.highlight}
You can use ``ArrayList`` instead of arrays whenever you don't know the size of the array you need or you know that you will add and remove items and may need to change the array’s size _dynamically_ during run time. An ``ArrayList`` is **mutable**, meaning it can change during run time by adding and removing objects from it.

<html>
<dl>
  <dt>ArrayList</dt>
  <dd>A re-sizable collection. It is called <code>ArrayList</code> because it stores the items that have been added to it in an underlying <strong>array</strong>. But it also takes care of keeping track of how many items have been added to the array and it will create a new bigger array under the covers when needed to hold more items.
  </dd>
</dl>
</html>

<html>
<dl>
  <dt>Mutable</dt>
  <dd>Can <strong>change</strong> during run time by adding and removing objects from it.
  </dd>
</dl>
</html>

### Packages and Imports

The ``ArrayList`` class is in the ``java.util`` package. A **package** is a set
or library of related classes. The classes we have used until now, such as
``String`` and ``Math``, are in the special package ``java.lang`` whose classes
are always available in any Java program. Other packages, such as ``java.util``,
provide classes that can only be used either by **importing** them or (much more
rarely) by referring to them by their full name which includes the package as a
prefix. The full name of ``ArrayList`` is thus ``java.util.ArrayList`` but
rather than type that out all the time, in any class where we want to use
``ArrayList`` we will usually import it with an ``import`` statement.

<div class="imp" markdown="block">

Import statements have to come _before_ the `class` definition in a Java source file and serve to tell Java which class you mean when you use a short name like ``ArrayList``. To import just one class we use a single ``import`` of the fully-qualified name of the class like this:

```java
import java.util.ArrayList;
```
> **AP EXAM NOTE:** Don't worry about adding `import` statements on the exam. Any that you need will be provided for you.

</div>

After such an import statement, anywhere ``ArrayList`` is used as a **class name** in the file it will be taken to mean ``java.util.ArrayList``.

### Declaring and Creating ArrayLists

To declare a ArrayList use ``ArrayList<Type> name`` where *Type*, called a
**type parameter** is the type of objects you want to store in the ArrayList.
For example a variable naming an ``ArrayList`` meant to hold ``String``\ s is
declared as ``ArrayList<String>`` as shown in the code below. You can declare a
variable to just be of type ``ArrayList``, with no type parameter, and it’ll be
approximately the same as if you had declared ``ArrayList<Object>``, but it is
good practice to specify the type of objects you intend to store in an
``ArrayList`` as it allows the compiler to find errors that would otherwise be
missed until run time.

.. code-block:: java

    // ArrayList<Type> name = new ArrayList<Type>();
    // An ArrayList of Strings:
    ArrayList<String> shoppingList = new ArrayList<String>();

.. note::

    ``ArrayList``\ s can only hold reference types like ``String``. Since they
    can’t hold primitive types like ``int`` and ``double``, if we want a
    collection of numbers we need to use the wrapper classes ``Integer`` or
    ``Double``. However, because of autoboxing, if you declare an
    ``ArrayList<Integer>`` or ``ArrayList<Double>`` you can mostly treat the
    elements of the ``ArrayList`` as if they were in fact ``int``\ s or
    ``double``\ s.

As with other reference types, declaring a ``ArrayList`` variable doesn't
actually create a ``ArrayList`` object. It only creates a variable that can
refer to a ``ArrayList`` or ``null``. To actually create a ``ArrayList`` we must
invoke a constructor such as ``new ArrayList<String>()``.

You can get the number of items in a ``ArrayList`` using the ``size()`` method.
Notice that a newly constructed ``ArrayList`` is empty and thus has a size of 0.
Also remember that you can’t call methods on ``null`` so trying to call ``size``
on the value of ``list2`` at line 10 below causes a ``NullPointerException``.

#### Wrapper Classes: Integer & Double

You can also create ArrayLists of integer and double values. However, you have
to use ``Integer`` or ``Double`` as the type parameter because ``ArrayList``\ s
can only hold objects, not primitive values. All primitive types must be
**wrapped** in objects before they are added to an ArrayList. For example,
``int`` values can be wrapped in ``Integer`` objects, ``double`` values can be
wrapped in ``Double`` objects. However this normally happens automatically
thanks to autoboxing.

```java
ArrayList<Integer> numList = new ArrayList<Integer>();
ArrayList<Double> decimalList = new ArrayList<Double>();
```

You can actually put in any kind of objects in an ``ArrayList``, including
instances of classes that you write, such as the ``Student``, ``Person``, or
``Pet`` classes from Unit 5.

---

## ⭐️ Summary

- ``ArrayList``s are re-sizable lists that allow adding and removing items to
  change their size during run time.

- The ``ArrayList`` class is in the ``java.util`` package. You must import
  ``java.util.ArrayList`` or ``java.util.*`` to use it.

- An ``ArrayList`` object contains object references and is mutable, meaning it
  can change (by adding and removing items from it).

- The ``ArrayList`` constructor ``ArrayList()`` constructs an empty list of size 0.

- Java allows the generic type ``ArrayList<E>``, where the generic type ``E``
  specifies the type of the elements, like ``String`` or ``Integer``. Without
  it, the type will be ``Object``.

- ``ArrayList<E>`` is preferred over ``ArrayList`` because it allows the
  compiler to find errors that would otherwise be found at run time.

- When ``ArrayList<E>`` is specified, the types of the reference parameters and
  return type when using its methods are type ``E``.

- ``ArrayList``s cannot hold primitive types like ``int`` or ``double``, so
  you must use the wrapper classes ``Integer`` or ``Double`` to put numerical
  values into an ``ArrayList``. However autoboxing usually takes care of that
  for you.

<div class="warn" markdown="block">

🛑 When class ends, don't forget to **SAVE YOUR WORK**!

1. Navigate to the `Source Control` menu on the _LEFT_ sidebar
2. Type a brief **commit message** in the box, for example: `updated Main.java`
3. Click the <button type="button" name="button" class="btn btn-green">commit changes</button> button on the _LEFT_ menu
4. Click the <button type="button" name="button" class="btn btn-green">sync changes</button> button on the _LEFT_ menu
5. _Finally you can close your Codespace!_

</div>

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
