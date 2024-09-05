---
layout: notes
title: "📓1.2: Printing & Debugging" 
parent: "1️⃣ Primitive Types"
nav_order: 2
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

## Print Methods

Java has two different methods to print **output** to the screen:

- **System.out.println(value)** : prints the value followed by a new line (ln)
- **System.out.print(value)** : prints the value without advancing to the next line

``System.out.println("Hi there!");`` prints out the characters between the first ``"`` and the second ``"`` followed by a new line.  

#### String Literals
{:.no_toc}

The ``"Hi there!"`` is called a **string literal**, and it can have zero to many characters enclosed in starting and ending double quotes.

### Syntax: the "grammar" of Java
Special words—also called **keywords**—such as ``public``, ``class``, and ``if`` must be in lowercase, but class names such as ``System`` and ``String`` are capitalized. 

Lines in a Java program that express a _complete action_ such as assigning a value to a variable must end with a semicolon (``;``). Such a line is called a **statement**. You can think of the semicolon (``;``) in Java like a period (``.``) in English. The same way you use a period to end a sentence in English, you use a semicolon to end a statement in Java.  

> You will not be penalized on the exam if you forget a needed semicolon but the Java compiler is not so lenient; your program won't compile without it.
>
> Note also that not *every* line ends with a semicolon; if the line starts a **construct** like an `if` statement, there is no semicolon before the opening ``{`` nor one after the closing ``}``.



---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
