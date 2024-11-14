---
layout: notes
title: "📓4.2: For Loops" 
parent: "4️⃣ Iteration"
nav_order: 2
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 4.2](https://runestone.academy/ns/books/published/csawesome/Unit4-Iteration/topic-4-2-for-loops.html?mode=browsing) 

<div class="setup" markdown="block">

📝 Take notes in a **Codespace** during class, coding along with the instructor.

1. Go to GitHub and click on your picture in the _TOP RIGHT_ corner
2. Select `Your repositories`
3. Open `CS2-Unit-4-Notes`
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` (unless you already have one listed there), wait for the environment to load, _then you're ready to code_!

</div>

---

## For Loops

Another type of loop in Java is a **for loop**. This is usually used when _you know how many times_ you want the loop to execute. It is often a simple **counter-controlled loop** to do the loop body a set number of times.

### Three Parts of a For Loop

<div class="imp" markdown="block">
  
A `for`-loop combines all 3 parts of writing a loop in one line to **initialize**, **test condition**, and **change** the loop control variable. The 3 parts are separated by **semicolons** (``;``):
```java
for (initialize; test condition; change) {
   loop body
}
```
</div>

> The `for`-loop is like a **shortcut** way to write a `while` loop, with **all three steps** that you need in one line.

![image](Figures/compareForAndWhile.png)

Watch the following <a href="https://www.youtube.com/watch?v=SEDnzXeb2hU&list=PLHqz-wcqDQIEP6p1_0wOb9l9aQ0qFijrP&index=9&ab_channel=colleenlewis"><button class="btn">📺 VIDEO</button></a> which **compares** a while loop and for loop line by line.

Here is a **control flow diagram** for a `for` loop:

![image](Figures/ForLoopFlow.png)
> * The code in the **initialization** area is executed only _one time_ before the loop begins
> * The **test condition** is _checked each time_ through the loop and the loop continues as long as the condition is `true`
> * The **loop control variable change** is done at the _end_ of each execution of the body of the loop, just like a `while` loop.
> * When the loop condition becomes `false`, execution will continue at the next statement _after_ the body of the loop.

{:.highlight}
Two common _patterns_ in `for`-loops are to **count from `0` up to an number** (using `<`) or **count from `1` to a number** including the number (using `<=`). Remember that if you start at 0 use `<`, and if you start at 1, use `<=`. 

The two loops below using these two patterns both run 10 times: 
```java
      // These loops both run 10 times
      // If you start at 0, use <
      for(int i = 0; i < 10; i++) {
         System.out.println(i);
      }
      // If you start at 1, use <=
      for(int i = 1; i <= 10; i++) {
         System.out.println(i);
      }
```
> The variable `i` (stands for **index**) is often used as a **counter** in `for`-loops.

### Decrementing Loops

You can also count **backwards** in a loop s_tarting from the last number_ and decrementing down to 0 or 1. All 3 parts of the loop must change to count backwards including the test of when to stop. 
> For example, ``for (int i=5; i > 0; i--)`` counts from 5 down to 1.

<div class="task" markdown="block">

What do you think will happen when you run the code below? How would it change if you changed line 11 to initialize `i`'s value to 3? 

```java
String line1 = " bottles of pop on the wall";
String line2 = " bottles of pop";
String line3 = "Take one down and pass it around";

// loop 5 times (5, 4, 3, 2, 1)
for (int i = 5; i > 0; i--) {
  System.out.println(i + line1);
  System.out.println(i + line2);
  System.out.println(line3);
  System.out.println((i - 1) + line1);
  System.out.println();
}
```


</div>

---

## ⭐️ Summary


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
