---
layout: notes
title: "📓4.5: Loops Analysis" 
parent: "4️⃣ Iteration"
nav_order: 5
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 4.5](https://runestone.academy/ns/books/published/csawesome/Unit4-Iteration/topic-4-5-loop-analysis.html?mode=browsing) 

<div class="setup" markdown="block">

📝 Take notes in a **Codespace** during class, coding along with the instructor.

1. Go to GitHub and click on your picture in the _TOP RIGHT_ corner
2. Select `Your repositories`
3. Open `CS2-Unit-4-Notes`
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` (unless you already have one listed there), wait for the environment to load, _then you're ready to code_!

</div>

---

## Loop Analysis

In this lesson, you will practice **tracing through code with loops** and analyzing loops to determine how many times they run.

### Tracing Loops

Let's practice tracing through loops with many variables. Remember to make a **tracing table** to keep track of all the variables, the iterations, and the output.

Here is a complex loop.  See if you can trace the code on paper by making a tracing table to predict what the code will do when you run it. Click on the this [Java visualizer](https://goo.gl/qEHnpg) link to help you step through the code.

<div class="task" markdown="block">
  
✏️ Can you trace through this code? Write your **tracing table** on paper first, then test the code.
> Add in output statements ``System.out.println("var1: " + var1 + " var2: " + var2);`` before the loop and inside the loop at the end to keep track of the variables and run. 

```java
int var1 = 3;
int var2 = 2;

while ((var2 != 0) && ((var1 / var2) >= 0))
{
  var1 = var1 + 1;
  var2 = var2 - 1;
}
```
</div>

<html>
<details>

<summary>✅ CHECK: Did your trace table look like the following?</summary>

<div markdown="block">

![image](Figures/whileLoopTrace.png)

</div>

</details>
</html>

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
