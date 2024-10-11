---
layout: notes
title: "📓3.7: Comparing Objects" 
parent: "3️⃣ Conditionals"
nav_order: 7
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 3.7](https://runestone.academy/ns/books/published/csawesome/Unit3-If-Statements/topic-3-7-comparing-objects.html?mode=browsing) 

<div class="setup" markdown="block">

📝 Take notes in a **Codespace** during class, coding along with the instructor.

1. Go to GitHub and click on your picture in the _TOP RIGHT_ corner
2. Select `Your repositories`
3. Open `CS2-Unit-3-Notes`
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` (unless you already have one listed there), wait for the environment to load, _then you're ready to code_!

</div>


## Comparing Objects

Comparing objects is a little different than comparing primitive typed values like numbers. Objects can be very complex and have many attribute values or instance variables inside them. For example, the ``Turtle`` objects have many instance variables like ``name``, ``width``, ``height``, ``xPos``, ``yPos``, etc. When comparing two ``Turtle`` objects, we need a specially written **equals** method to compare all of these values. In this lesson, we will take a look at ``String`` objects and the difference between comparing them with ``==`` vs. the ``equals`` method.

### String Equality

The **equals** method for Strings compares two strings letter by letter. ``s1.equals(s2)`` is true if ``s1`` and ``s2`` have all the same characters in the same order. With ``Strings`` and other objects, you almost always use ``equals`` instead of ``==`` to check their equality.

When the operator ``==`` is used to compare object variables, it returns true when the two variables *refer to the same object*. These variables are called **object references** and **aliases** for the same object. With strings this happens when one string variable is set to another.


![image](Figures/stringEquality.png)

### Equality with New Strings
{:.no_toc}

If you use the ``new`` keyword to create a string, it will always create a new string object. So, even if we create two string objects with new that contain all the same characters in the same order, they will not refer to the same object.

Watch this [video](https://www.youtube.com/watch?v=xZroaSGhgxA) to see how this code works in memory. 
> Since we used the ``new`` keyword, two different ``String`` objects will be created that each have the characters ``Hello`` in them.  So ``s1 == s2`` will be false since they don't refer to the same object, but ``s1.equals(s2)`` is true since the two different objects contain the same characters in the same order.


Here is the representation of these String objects in memory:

![image](Figures/s1ands2.jpg)

{:.warning}
Only use ``==`` with primitive types like ``int`` or to test if two strings (or objects) refer to the same object.  Use ``equals``, not ``==``, with strings to test if they are equal letter by letter.

### Comparing with null

One common place to use ``==`` or ``!=`` with objects is to compare them to **null** to see if they really exist. Sometimes short-circuit evaluation is used to avoid an error if the object doesn't exist. Remember that **short-circuit evaluation** is used with ``&&`` in Java meaning that if the first part of the if condition is false, it doesn't even have to check the second condition and it knows the whole ``&&`` test is false.

---

## ⭐️ Summary

- Often classes have their own **equals** method, which can be used to determine whether two objects of the class are equivalent.

- Two object references are considered **aliases** when they both reference the same object.

- Object reference values can be compared, using ``==`` and ``!=``, to identify aliases.

- A reference value can be compared with null, using ``==`` or ``!=``,  to determine if the reference actually references an object.


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
