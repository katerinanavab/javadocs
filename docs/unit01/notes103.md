---
layout: notes
title: "📓1.3: Variables & Data Types" 
parent: "1️⃣ Primitive Types"
nav_order: 3
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

## Variables and Data Types

📦 A **variable** is a name associated with a memory location in the computer, where you can store a **value** that can change or vary. 

> _Example:_ When you play a game, it will often have a score. Scores often start at 0 and increase, so they can change. A score can be stored in a variable.


### Data Types
{:.no_toc}

A type is a set of **values** (a domain) and a set of possible **operations** on them. For example, you can do subtraction operations with ``int``s and ``double``s, but not with ``boolean``s and ``String``s.

There are two categories of variables in Java: 
  1. **Primitive variables** that hold primitive data types
  2. **Object or reference variables** that hold a _reference_ to an object of a class (more on **objects** in the next unit - they are more complex data types).
> A reference is a way to find the object in the computer's memory (like a UPS tracking number helps you find your package).

The types tested on the AP CS A exam are:

- ``int`` which can represent integers, i.e. whole numbers with no fractional part
  such as 3, 0, -76, and 20393.

- ``double`` which can represent non-integer numbers like 6.3 -0.9, and
  60293.93032.

- ``boolean`` which can represent only two values: ``true`` and ``false``. (The
  data type is named for [George Boole](https://en.wikipedia.org/wiki/George_Boole), a 19th century English
  mathematician who invented Boolean algebra, a system for dealing with
  statements made up of only true and false values.)

- ``String`` is one of the **object** types on the exam and is the name of a **class** built-into Java. A ``String`` is written in a Java program as a sequence of characters enclosed in a pair of double quotes - like ``"Hello"``.

### Declaring Variables in Java

To create a variable, you must tell Java its data type and its name.  Creating a variable is also called **declaring a variable**.  The type is a keyword like int, double, or boolean, but you get to make up the name for the variable.  When you create a **primitive variable** Java will set aside enough bits in memory for that primitive type and associate that memory location with the name that you used.

Computers store all values using **bits** (binary digits).  A **bit** can represent two values and we usually say that the value of a bit is either 0 or 1. When you declare a variable, you have to tell Java the type of the variable because Java needs to know how many bits to use and how to represent the value.  The 3 different primitive types
all require different number of bits.  An integer gets 32 bits of memory, a double gets 64 bits of memory and a boolean could be represented by just one bit.

![](variables.png)

To **declare** (create memory space for) a variable, you specify the type, leave at least one space, then the name for the variable and end the line with a semicolon (``;``). 
> Java uses the keyword **int** for integer, **double** for a floating point number (a double precision number), and **boolean** for a Boolean value (true or false).

Here is an example **declaration** of a variable called `score`:

```java
  int score;
```

![](https://higherlogicdownload.s3.amazonaws.com/CASACT/SociousInlineImages/f93d86f6dbf14fdd85222d321e79b22d_yjvxdxcg.jpg)

After declaring a variable, you can give it a value like below using an equals sign ``=`` followed by the value. This is called **assignment**.

```java
  int score;
  score = 4;
```

Or you can set an initial value for the variable in the variable declaration. Here is an example that shows declaring a variable and **initializing** it all in a single statement:

```java
  int score = 4;
```

🖨️ When you are printing out variables, you can use the **string concatenation** operator ``+`` to add them to another String inside `System.out.print`. Never put variables inside quotes ``""`` because that will print out the variable name letter by letter. You do not want to print out the variable name, but the _value_ of the variable in memory.

### Naming Variables

While you can name your variable almost anything, there are some rules.  A variable name must start with an alphabetic character (like a, b, c, etc.) and can include letters, numbers, and underscores ``_``. It must be all one word with **no spaces**.

🚫 You can't use any of the **keywords** or **reserved** words as variable names in Java (``for``, ``if``, ``class``, ``static``, ``int``, ``double``, etc). 

The name of the variable should _describe the data_ it holds.  A name like ``score`` helps make your code easier to read. A name like ``x`` is not a good variable name in programming, because it gives no clues as to what kind of data it holds. 

The capitalization convention in Java and many programming languages is to always start a variable name with a lower case letter and then uppercase the first letter of each additional word, for example ``gameScore``. 

<div class="imp" markdown="block">
  
* Use **meaningful** variable names!
* Start variable names with a **lowercase** letter and use `camelCase`.
* Variable names are case-sensitive and spelling sensitive! Each use of the variable in the code must match the variable name in the declaration exactly.
* Never put variables inside quotes (" ").

</div>

---

## ⭐️ Summary

- A **variable** is a name for a memory location where you can store a value that can change or vary.
- A variable can be **declared** and **initialized** with the following code:

```java
  int score;
  double gpa = 3.5;
```

- **Data types** can be primitive types or reference types (like `String`).
- The three primitive data types used in this course are `int` (integer numbers), `double` (decimal numbers), and `boolean` (true or false).
- Each variable has associated memory that is used to hold its **value**.
- The memory associated with a variable of a primitive type holds an actual primitive value.
- When a variable is declared `final`, its value cannot be changed once it is initialized.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
