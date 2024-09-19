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


In Java you can also use just a **string literal**, which is a set of characters enclosed in double quotes (``"``), to create a ``String`` object.

```java
String greeting = "Hello";
```

In both cases an _object_ of the ``String`` _class_ will be created in memory, and the **value** of the variable `greeting` will be set to an object **reference** (👉 a way to find that object).

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
