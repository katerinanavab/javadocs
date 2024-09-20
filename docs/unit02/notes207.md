---
layout: notes
title: "📓2.7: String Methods" 
parent: "2️⃣ Using Objects"
nav_order: 7
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 2.7](https://runestone.academy/ns/books/published/csawesome/Unit2-Using-Objects/topic-2-7-string-methods.html?mode=browsing) 

<div class="setup" markdown="block">

📝 Take notes in a **Codespace** during class, coding along with the instructor.

1. Go to GitHub and click on your picture in the _TOP RIGHT_ corner
2. Select `Your repositories`
3. Open `CS2-Unit-2-Notes`
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` (unless you already have one listed there), wait for the environment to load, _then you're ready to code_!

</div>



## String Methods

A string holds **characters in a sequence**. Each character is at a position, or **index**, which starts with `0` as shown below.  An **index** is a number associated with a position in a string. The **length** of a string is the _number of characters_ in it including any spaces or special characters. The string below has a `length` of 14:

![image](figures/stringIndicies.png)

{:.important}
The _first_ character in a String is at **index** `0` and the _last_ character is at `length - 1`.

For the AP CSA exam, you only need to know how to use the following String **methods**.  All of the String method descriptions are included in the <a href="https://apstudents.collegeboard.org/ap/pdf/ap-computer-science-a-java-quick-reference_0.pdf" target="_blank">AP CSA Java Quick Reference Sheet</a> that you get during the exam so you don't have to memorize these.


-  `int length()` method returns the number of characters in the string, including spaces and special characters like punctuation.

-  `String substring(int from, int to)` method returns a new string with the characters in the current string starting with the character at the ``from`` index and ending at the character *before* the ``to`` index (if the ``to`` index is specified, and if not specified it will contain the rest of the string).

-  `int indexOf(String str)` method searches for the string ``str`` in the current string and returns the index of the beginning of ``str`` in the current string or -1 if it isn't found.

-  `int compareTo(String other)` returns a negative value if the current string is less than the ``other`` string alphabetically, 0 if they have the same characters in the same order, and a positive value if the current string is greater than the ``other`` string alphabetically.

-  `boolean equals(String other)` returns true when the characters in the current string are the same as the ones in the ``other`` string.  This method is inherited from the Object class, but is **overridden** which means that the String class has its own version of that method.

### length, substring, indexOf

Test the code below to see the output from the String methods ``length``, ``substring``, and ``indexOf``. The length method returns the number of characters in the string, not the last index which is length -1. The ``str.substring(from,to)`` method returns the substring from the ``from`` index up to (but not including) the ``to`` index. The method ``str.indexOf(substring)`` searches for the substring in str and returns the index of where it finds substring in str or -1 if it is not there.

<div class="task" markdown="block">
           
This code shows the output from String methods `length`, `substring`, and `indexOf`. 

💬 **Discuss:** How many letters does substring(0,3) return? What does indexOf return when its argument is not found?

```java
String message1 = "This is a test";
String message2 = "Hello Class";

System.out.println(message1.length());
System.out.println(message2.length());

System.out.println(message1.substring(0, 3));
System.out.println(message1.substring(2, 3));
System.out.println(message1.substring(5));

System.out.println(message1.indexOf("is")); // This will match the is in "This"!
System.out.println(message1.indexOf("Hello"));
System.out.println(message2.indexOf("Hello"));

// lowercase and uppercase methods are not on the AP exam, but still useful
System.out.println(message2.toLowerCase());
System.out.println(message2.toUpperCase());
```
</div>

{:.highlight}
Remember that `substring(from,to)` does not include the character at the ``to`` index! To return a single character at index i, use ``str.substring(index, index + 1)``.
   
### CompareTo and Equals

We can compare _primitive types_ like `int` and `double` using **operators** like ``==`` and ``<`` or ``>``, which you will learn about in the next unit. However, with _reference types_ like `String`, you must use the **methods** ``equals`` and ``compareTo``, not ``==`` or ``<`` or ``>``.

The method ``compareTo`` compares two strings character by character. If they are equal, it returns 0. If the first string is alphabetically ordered before the second string (which is the argument of ``compareTo``), it returns a negative number. And if the first string is alphabetically ordered after the second string, it returns a positive number. (The actual number that it returns does not matter, but it is the distance in the first letter that is different, e.g. A is 7 letters away from H.)

![image](figures/compareTo.png)

The ``equals`` method compares the two strings character by character and returns ``true`` or ``false``. Both ``compareTo`` and ``equals`` are case-sensitive. There are case-insensitive versions of these methods, ``compareToIgnoreCase`` and ``equalsIgnoreCase``, which are not on the AP exam.

<div class="task" markdown="block">
  
Test the code below to see the output from ``compareTo`` and ``equals``. 

```java
String message = "Hello!";

System.out.println(message.compareTo("Hello!"));
System.out.println(message.compareTo("And"));
System.out.println(message.compareTo("Zoo"));

System.out.println(message.equals("Hello!"));
System.out.println(message.equals("hello!"));
```

</div>

> Since ``"Hello!"`` would be alphabetically ordered after ``"And"``, ``compareTo`` returns a positive number. Since ``"Hello!"`` would be alphabetically ordered before ``"Zoo"``, ``compareTo`` returns a negative number.  Notice that ``equals`` is case-sensitive.

There are lots of other methods in the String class.  You can look through the Java documentation for the |String class| online.   You don't have to know all of these for the exam, but you can use them if you want to on the exam.

An **Application Programming Interface (API)** is a library of prewritten classes that simplify complex programming tasks for us. These classes are grouped together in a **package** like java.lang and we can import these packages (or individual classes) into our programs to make use of them. For instance, we have just discussed the String library built into the default java.lang package - it takes care of the detailed work of manipulating strings for us.  There are many other useful library packages as well, both in the java.lang package and in other packages. Documentation for APIs and libraries are essential to understanding how to use these classes.

{.highlight}
Strings are **immutable** which means that they can't change after creation. Anything that you do to **modify** a string (like creating a substring or appending strings) _returns a new string_.


### Common Mistakes with Strings

Here is a list of common mistakes made with Strings.

-  Thinking that substrings include the character at the last index when they don't.

-  Thinking that strings can change when they can't.  They are immutable.

- Trying to access part of a string that is not between index 0 and length -1. This will throw an IndexOutOfBoundsException.

-  Trying to call a method like ``indexOf`` on a string reference that is null.  You will get a null pointer exception.

-  Using ``==`` to test if two strings are equal.  This is actually a test to see if they refer to the same object.  Usually you only want to know if they have the same characters in the same order.  In that case you should use ``equals`` or ``compareTo`` instead.
-  Treating upper and lower case characters the same in Java.  If ``s1 = "Hi"`` and ``s2 = "hi"`` then ``s1.equals(s2)`` is false.


#### String Methods Game
{:.no_toc}

<div class="task" markdown="block">

Try the game below written by AP CSA teacher Chandan Sarkar. Click on **Strings** and then on the letters that would be the result of the string method calls. We encourage you to work in pairs and see how high a score you can get.

<a href="https://csa-games.netlify.app/" target="_blank">game</a>

</div>

---

## ⭐️ Summary

<br>

<div class="warn" markdown="block">

🛑 When class ends, don't forget to **SAVE YOUR WORK**!

1. Navigate to the `Source Control` menu on the _LEFT_ sidebar
2. Click the <button type="button" name="button" class="btn btn-green">commit changes</button> button on the _LEFT_ menu
3. Type a brief **commit message** at the top of the file that opens, for example: `updated Main.java`
4. Click the small `✔️` **checkmark** in the _TOP RIGHT_ corner
5. Click the <button type="button" name="button" class="btn btn-green">sync changes</button> button on the _LEFT_ menu
6. _Finally you can close your Codespace!_

</div>

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
