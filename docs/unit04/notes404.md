---
layout: notes
title: "📓4.4: Nested Loops" 
parent: "4️⃣ Iteration"
nav_order: 4
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 4.4](https://runestone.academy/ns/books/published/csawesome/Unit4-Iteration/topic-4-4-nested-loops.html?mode=browsing) 

<div class="setup" markdown="block">

📝 Take notes in a **Codespace** during class, coding along with the instructor.

1. Go to GitHub and click on your picture in the _TOP RIGHT_ corner
2. Select `Your repositories`
3. Open `CS2-Unit-4-Notes`
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` (unless you already have one listed there), wait for the environment to load, _then you're ready to code_!

</div>

---

## Nested For Loops

A **nested loop** has _one loop inside of another_. These are typically used for working with two dimensions such as printing stars in rows and columns as shown below:

![image](Figures/nestedloops.png)

When a loop is _nested inside_ another loop, the inner loop runs many times inside the outer loop. In each iteration of the **outer loop**, the **inner loop** will be _re-started_. 

{:.highlight}
The **inner loop** must finish all of its iterations _before_ the **outer loop** can continue to its next iteration!

💬 **DISCUSS:** What does the following code print out? Watch the code run in the [Java visualizer](http://www.pythontutor.com/visualize.html#code=public%20class%20NestedLoops%0A%7B%0A%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%0A%20%20%20%7B%0A%20%20%20%20%20%20%20for%20%28int%20row%20%3D%201%3B%20row%20%3C%3D%203%3B%20row%2B%2B%29%0A%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20for%20%28int%20col%20%3D%201%3B%20col%20%3C%3D%205%3B%20col%2B%2B%29%0A%20%20%20%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20System.out.print%28%22*%22%29%3B%0A%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%20%20%20System.out.println%28%29%3B%0A%20%20%20%20%20%20%20%7D%0A%20%20%20%7D%0A%7D&cumulative=false&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false&curInstr=0). 
> Notice how the **inner loop is started over** for each `row`. Can you predict how many rows and columns of stars there will be?

```java
for (int row = 1; row <= 3; row++) {
    for (int col = 1; col <= 5; col++) {
        System.out.print("*");
    }
    System.out.println();
}
```
> Can you change the code to print a rectangle with 10 rows and 8 columns of stars? You can also try replacing line 10 with this print statement to see the rows and columns: ``System.out.print(row + "-" + col + " ");``

### Nested Loops with Turtles

❄️ Try nested loops with `Turtle` objects to create a snowflake design!

#### 💻 In-Class Activity: Turtle Snowflakes
{:.no_toc}

<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit4-Iteration/topic-4-4-nested-loops.html?mode=browsing"><button type="button" name="button" class="btn">CSAwesome Topic 4.4</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: Turtle Snowflake** activity in pairs.

</div>

---

## ⭐️ Summary

- **Nested iteration statements** are iteration statements that appear in the body of another iteration statement.

- When a loop is nested inside another loop, the inner loop must complete all its iterations before the outer loop can continue.

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
