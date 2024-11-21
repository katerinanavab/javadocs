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

### Counting Loop Iterations

Loops can be also analyzed to determine how many times they run. This is called **run-time analysis** or a **statement execution count**.

<div class="task" markdown="block">
  
✏️ How many stars are printed out in this loop? How many times does the loop run? Figure it out on paper before you run the code.

```java
for (int i = 3; i < 7; i++)
{
    System.out.print("*");
}
```
</div>

> If you made a trace table, you would know that the loop runs when i = 3, 4, 5, 6 but finishes as soon as i becomes 7 since that is not less than 7. So, the loop runs 4 times. Or you can use the shortcut formula in the note below.

<div class="imp" markdown="block">

💡 The **number of times** a loop executes can be calculated by: `(largestValue - smallestValue + 1)`

- If the loop uses `counter <= limit` as the condition, `limit` is the **largest** value.
- If the loop uses `counter < limit`, `limit-1` is the **largest** value that allows the loop to run.
  
</div>

> In the code above the **largest** value that allows the loop to run is 6 (which is the largest value < 7) and the **smallest** value that allows the loop to execute is 3 so this loop executes (6 - 3 + 1 = 4 times).

<div class="task" markdown="block">
  
✏️ How many stars are printed out in this loop? How many times does the loop run? Figure it out on paper before you run the code.

```java
for (int row = 0; row < 5; row++)
{
    for (int col = 0; col < 10; col++)
    {
        System.out.print("*");
    }
    System.out.println();
}
```
</div>

{:.highlight}
The **number of times a nested for loop body is executed** is equal to the number of times the outer loop runs multiplied by the number of times the inner loop runs (`OuterLoopRuns * InnerLoopRuns`).

> For the example above, the outer loop executes 4 - 0 + 1 = 5 times and the inner 9 - 0 + 1 = 10 times so the total is 5 * 10 = 50.


#### Loop Analysis Game
{:.no_toc}

<div class="task" markdown="block">

🎲 Try the game below to practice loop analysis. Click on **Loops** and click on the number of times the loop runs. For an added challenge, try the check boxes for `Backwards` and `Nested`. We encourage you to work in pairs and see how high a score you can get.

<a href="https://csa-games.netlify.app/" target="_blank"><button class="btn">Loop Analysis Game</button></a>

</div>

---

## ⭐️ Summary

- A trace table can be used to keep track of the variables and their values throughout each iteration of the loop.

- We can determine the number of times a code segment will execute with a **statement execution count**. This is called **run-time analysis**.

- The number of times a loop executes can be calculated by ``largestValue - smallestValue + 1`` where these are the largest and smallest values of the loop counter variable possible in the body of the loop.

- The number of times a nested for-loop runs is the number of times the outer loop runs **times** the number of times the inner loop runs.

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
