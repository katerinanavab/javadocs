---
layout: notes
title: "📓2.6: The String Class" 
parent: "2️⃣ Using Objects"
nav_order: 6
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 2.6](https://runestone.academy/ns/books/published/csawesome/Unit2-Using-Objects/topic-2-6-strings.html?mode=browsing) 

<div class="setup" markdown="block">

📝 Take notes in a **Codespace** during class, coding along with the instructor.

1. Go to GitHub and click on your picture in the _TOP RIGHT_ corner
2. Select `Your repositories`
3. Open `CS2-Unit-2-Notes`
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` (unless you already have one listed there), wait for the environment to load, _then you're ready to code_!

</div>


## The String Class


**Strings** in Java are _objects_ of the ``String`` _class_ that hold **sequences of characters** (`a`, `B`, `c`, `$`, etc). You can declare a variable to be of the type ``String``.

> Remember that a **class** (or classification) in Java defines the data that all **objects** of the class have (the _instance variables_) and the behaviors, the things that objects know how to do (the _methods_).

![image](figures/stringbracelet.png)

{:.highlight}
Class names in Java, like ``String``, begin with a _CAPITAL_ letter.  All primitive types: ``int``, ``double``, and ``boolean``, begin with a _lowercase_ letter. This is one easy way to tell the difference between primitive types and class types.

In Java there are two ways to create an object of the ``String`` class. You can use the ``new`` keyword followed by a space and then the class constructor and then in parentheses you can include values used to initialize the fields of the object. 

```java
String greeting = new String("Hello World");
```
> This is the standard way to **create a `new` object of any class** in Java.

<div class="imp" markdown="block">
  
In Java you can also use just a **string literal**, which is a set of characters enclosed in double quotes (``" "``), to create a ``String`` object:

```java
String greeting = "Hello";
```

</div>

In both cases an _object_ of the ``String`` _class_ will be created in memory, and the **value** of the variable `greeting` will be set to an object **reference** (👉 a way to find that object).

![image](figures/stringObject.png)

### String Concatenation

``String``s can be added to each other to create a new string using the ``+``
or ``+=`` operator . This is also called **appending** or **concatenating**. You
can also add any other kind of value to a ``String`` with ``+`` or ``+=`` and
the other value will be converted to a ``String`` automatically. Objects are
converted by calling their ``toString`` method which we'll talk about in section
5.4.

![image](https://i.etsystatic.com/42623235/r/il/0c61d4/5831105772/il_570xN.5831105772_8z3q.jpg)

Remember, however, that ``String``s are **immutable**, just like ``int``s and
``double``s. So when we add two ``String``s (or a ``String`` and another
value converted to a ``String``) we get a new ``String`` without making any
change to the values being added together just like when we add `1 + 2` the
original `1` and `2` aren't changed. When we use ``+=`` we are making a new
``String`` by adding something to the current value of a variable and then
assigning that new value back into the variable, again just like with numbers.

{:.highlight}
Note that spaces are not added between strings automatically.  If you want a space between two strings then add one using + " " +. If you forget to add spaces, you will get smushed output like "HiJose" instead of "Hi Jose".  And remember that variables are never put inside the quotes ("") since this would print the variable name out letter by letter instead of its value.

You can even add other items to a string using the ``+`` operator. Primitive
values like ``int`` and ``boolean`` will be converted to a ``String`` like what
you would type into a Java program and objects will be converted to ``String`` using the
``toString`` method discussed in the previous section.

<div class="task" markdown="block">

💬 **Discuss:** What do you think the following code will print out?

```java
String message = "12" + 4 + 3;
System.out.println(message);
```

</div>

{:.highlight}
If you are appending a number to a string it will be converted to a string first before being appended.

Since the same operators are processed from left to right this will print ``1243``.  First 4 will be turned into a string and appended to 12 and then 3 will be turned into a string and appended to 124.  If you want to do addition instead, try using parentheses!

What if you wanted to print out a double quote " character? Since the double quote " is a special character with meaning in Java, we put in a backslash in front of the quote to signal that we want just the character. This is called a **backslash escape sequence**. And if you wanted to print out a backslash, you would have to backslash it too in order to escape its special meaning. Another useful backslashed character is backslash \\n which will put in a newline.

   
---

## ⭐️ Summary

- **Strings** in Java are objects of the ``String`` class that hold sequences of characters.

- String objects can be created by using string literals (String s = "hi";) or by calling the String class constructor (String t = new String("bye");).

- **new** is used to create a new object of a class.
- **null** is used to indicate that an object reference doesn't refer to any object yet.

- String objects can be concatenated using the ``+`` or ``+=`` operator, resulting in a new String object.

- Primitive values can be concatenated with a String object. This causes implicit conversion of the values to String objects.

- Escape sequences start with a backslash ``\`` and have special meaning in Java. Escape sequences used in this course include ``\"``, ``\\``, and  ``\n`` to print out a quote, backslash, and a new line.

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
