---
layout: notes
title: "📓3.4: Else If Statements" 
parent: "3️⃣ Conditionals"
nav_order: 4
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 3.4](https://runestone.academy/ns/books/published/csawesome/Unit3-If-Statements/topic-3-4-else-ifs.html?mode=browsing) 

<div class="setup" markdown="block">

📝 Take notes in a **Codespace** during class, coding along with the instructor.

1. Go to GitHub and click on your picture in the _TOP RIGHT_ corner
2. Select `Your repositories`
3. Open `CS2-Unit-3-Notes`
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` (unless you already have one listed there), wait for the environment to load, _then you're ready to code_!

</div>


## Multi-Selection: else-if Statements

Using if/else statements, you can even pick between 3 or more possibilites. Just add **else if** for each possibility after the first **if**, and **else** before the last possibility.

```java
// 3 way choice with if, else if, else
if (boolean expression) {
  statement1;
}
else if (boolean expression) {
  statement2;
}
else {
  statement3;
}
```

<div class="task" markdown="block">

Run the code below and try changing the value of `x` to get each of the three possible lines in the conditional to print.
```java
int x = 2;
if (x < 0) {
  System.out.println("x is negative");
}
else if (x == 0) {
  System.out.println("x is 0");
}
else {
  System.out.println("x is positive");
}
System.out.println("after conditional");
```
</div>

Here is a flowchart for a conditional with 3 options like in the code above:

![image](Figures/Condition-three.png)

{:.highlight}
Another way to handle 3 or more conditional cases is to use the ``switch`` and ``case`` keywords, but these will not be on the exam. For a tutorial on using switch see the [Java Documentation](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/switch.html).

<div class="task" markdown="block">

Finish the following code so that it prints "Plug in your phone!" if the battery is below 50, "Unplug your phone!" if it is equal to 100, and "All okay!" otherwise. Change the battery value to test all 3 conditions.

```java
int battery = 60;

System.out.println("All okay!");
```
</div>

---

## ⭐️ Summary

- A multi-way selection is written when there are a series of conditions with different statements for each condition.

- Multi-way selection is performed using if-else-if statements such that exactly one section of code is executed based on the first condition that evaluates to true.

```java
// 3 way choice with if, else if, else
if (boolean expression) {
  statement1;
}
else if (boolean expression) {
  statement2;
}
else {
  statement3;
}
```

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
