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
> The code in the **initialization** area is executed only one time before the loop begins, the **test condition** is checked each time through the loop and the loop continues as long as the condition is `true`, and the **loop control variable change** is done at the _end_ of each execution of the body of the loop, just like a `while` loop.  When the loop condition is `false`, execution will continue at the next statement after the body of the loop.

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
