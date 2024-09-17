---
layout: notes
title: "📓2.2: Constructors" 
parent: "2️⃣ Using Objects"
nav_order: 2
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 2.2](https://runestone.academy/ns/books/published/csawesome/Unit2-Using-Objects/topic-2-2-constructors.html?mode=browsing) 

<div class="setup" markdown="block">

📝 Take notes in a **Codespace** during class, coding along with the instructor.

1. Go to GitHub and click on your picture in the _TOP RIGHT_ corner
2. Select `Your repositories`
3. Open `CS2-Unit-2-Notes`
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` (unless you already have one listed there), wait for the environment to load, _then you're ready to code_!

</div>

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

## Constructors: Creating and Initializing Objects

A Java class defines what objects of the class know (attributes) and what they can do (behaviors).  Each class has **constructors** like ``World()`` and ``Turtle(habitat)`` which are used to initialize the attributes in a newly created object.

A new object is created with the ``new`` keyword followed by the class name (``new Class()``).  When this code executes, it creates a new object of the specified class and calls a constructor, which has the same name as the class.  For example, ``new World()`` creates and initializes a new object of the ``World`` class, and ``new Turtle(habitat)`` creates and initializes a new ``Turtle`` object in the World habitat.

To create a new object and call a constructor write:

```java
    // ClassName variableName = new ClassName(parameters);
    World habitat = new World();    // create a new World object
    Turtle t = new Turtle(habitat); // create a new Turtle object
```

### Overloading Constructors


---

## ⭐️ Summary


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
