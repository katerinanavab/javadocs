---
layout: notes
title: "📓3.5: Compound Booleans" 
parent: "3️⃣ Conditionals"
nav_order: 5
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 3.5](https://runestone.academy/ns/books/published/csawesome/Unit3-If-Statements/topic-3-5-compound-ifs.html?mode=browsing) 

<div class="setup" markdown="block">

📝 Take notes in a **Codespace** during class, coding along with the instructor.

1. Go to GitHub and click on your picture in the _TOP RIGHT_ corner
2. Select `Your repositories`
3. Open `CS2-Unit-3-Notes`
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` (unless you already have one listed there), wait for the environment to load, _then you're ready to code_!

</div>


## Compound Boolean Expressions

### And (`&&`) Operator

What if you want **two things to be true** before the body of the conditional is executed?  Use ``&&`` as a logical **and** to join two Boolean expressions and the body of the condition will only be executed only if both are true.

<div class="task" markdown="block">
  
What if you want to go out and your parents say you can go out if you clean your room and do your homework? Test the code below and try different values for ``cleanedRoom`` and ``didHomework`` and see what they have to be for it to print ``"You can go out"``.
```java
boolean cleanedRoom = true;
boolean didHomework = false;

if (cleanedRoom && didHomework) {
  System.out.println("You can go out");
}
else {
  System.out.println("No, you can't go out");
}
```

</div>

### Or (`||`) Operator

What if it is okay if _only one of two things_ is true? Use ``||`` as a logical **or** to join two Boolean expressions and the body of the condition will be executed if one or both are true.

<div class="task" markdown="block">
  
For example, your parents might say you can go out if you can walk or they don't need the car.  Try different values for ``walking`` and ``carIsAvailable`` and see what the values have to be to print ``"You can go out"``.
```java
boolean walking = false;
boolean carIsAvailable = false;

if (walking || carIsAvailable) {
  System.out.println("You can go out");
}
else {
  System.out.println("No, you can't go out");
}
```

</div>

### Not (`!`) Operator

The **not** (``!``) operator can be used to negate a boolean value. We've seen ``!`` before in ``!=`` (not equal).  

<div class="task" markdown="block">

The code below says if homework is _not_ done, you can't go out. Try different values for ``homeworkDone``.
```java
boolean homeworkDone = false;
if (!homeworkDone) {
  System.out.println("Sorry, you can't go out!");
}
```

</div>

{:.warning}
If you use ``!`` in expressions with ``&&`` and ``||``, be careful because the results are often the opposite of what you think it will be at first. We'll see examples of this in the next lesson.

{:.highlight}
In Java, `!` will be executed before `&&`, and `&&` will be executed before `||`, unless there are **parentheses**. Anything inside parentheses is executed first.

### Truth Tables

#### AND (&&) TRUTH TABLE
{:.no_toc}

The following table (also called a **truth table**) shows the result for ``P && Q`` when ``P`` and ``Q`` are both expressions that can be ``true`` or ``false``. An expression involving logical operators like ``P && Q`` evaluates to a ``boolean`` value, ``true`` or ``false``. As you can see below the result of ``P && Q`` is only ``true`` if both ``P`` and ``Q`` are ``true``.

| P     | Q     | P && Q    |
|=======|=======|===========|
|true   |true   |true       |
|-------|-------|-----------|
|true   |false  |false      |
|-------+-------|-----------|
|false  |true   |???        |
|-------|-------|-----------|
|false  |false  |false      |

> 💬: The truth table above is missing one result.  What is the result of ``P && Q`` when ``P = false`` and ``Q = true``?

#### OR (||) TRUTH TABLE

The following table shows the result for ``P || Q`` when ``P`` and ``Q`` are both expressions that can be ``true`` or ``false``.  As you can see below the result of ``P || Q`` is ``true`` if either ``P`` or ``Q`` is ``true``.  It is also ``true`` when both of them are ``true``.

| P     | Q     | P || Q    |
|=======|=======|===========|
|true   |true   |true       |
|-------|-------|-----------|
|true   |false  |true       |
|-------+-------|-----------|
|false  |true   |???        |
|-------|-------|-----------|
|false  |false  |false      |

> 💬: The truth table above is missing one result.  What is the result of ``P || Q`` when ``P = false`` and ``Q = true``?

### Short Circuit Evaluation

![image](https://lirp.cdn-website.com/d7a1ea03/dms3rep/multi/opt/What-is-a-short-circuit--ACDC-Electric-llc-640w.jpg)

Both ``&&`` and ``||`` use **short circuit evaluation**.  That means that the second expression (on the right of the operator) isn't necessarily checked, if the result from the first expression is enough to tell if the compound boolean expression is true or false:

- If two boolean values/expressions are combined with a logical **or** (``||``) and the first expression is ``true``, then the second expression won’t be executed, since only one needs to be ``true`` for the result to be ``true``.
- If two boolean values/expressions are combined with a logical **and** (``&&``) and the first expression is ``false``, then the second expression won't be executed.  If the first expression is ``false``, the result will be ``false``, since both sides of the ``&&`` need to be ``true`` for the result to be ``true``.

<div class="task" markdown="block">

1. What is printed when the following code executes and x has been set to 0 and y to 3?
```java
if (x > 0 && (y / x) == 3) {
  System.out.println("first case");
}
else {
  System.out.println("second case");
}
```
2. What is printed when the following code executes and x has been set to zero and y is set to 3?
```java
if (x == 0 || (y / x) == 3) {
  System.out.println("first case");
}
else {
  System.out.println("second case");
}
```

</div>
  
#### Venn Diagram Activity
{:.no_toc}

📝 Explore the following problems in a group of 4:

1. Draw or print a [Venn diagram](https://docs.google.com/document/d/1lpjk0LS_KdAddRurMayJZmaFzeyEg4FyhviZcSTXvtU/edit?usp=sharing) of 4 intersecting circles. Put the names of the 4 people in your group one in each circle. Write down the age of each person in your group in the circles. If two or more people are the same age, put the age in the intersecting parts of their circles. Write a Boolean expression that compares the age of each person in the group using ``==``, ``<``, ``>``, and ``&&``, for example Ada's age ``>`` Alan's age ``&&`` Alan's age ``==`` Grace's age. Then, ask each person in your group their favorite movie. If two or more people have the same favorite movie, put the movie in the intersecting parts of their circles. Write a Boolean expression that compares the favorite movies in the group using ``==``, ``!=``, and ``&&``, for example Ada's movie ``==`` Alan's movie ``&&`` Alan's movie ``!=`` Grace's movie. Think of 1 more comparison and write it in the circles and as a Boolean expression. Share the Boolean expressions with the class.
   
3. Write the sentence "If it's sunny, OR if the temperature is greater than 80 and it's not raining, I will go to the beach." as a Java if statement using an int variable ``temperature`` and boolean variables ``sunny`` and ``raining``.  If the conditional is true, print out "Go to the beach!". So, you will go to the beach on days that it is sunny in any temperature, or you will go to the beach on days when the temperature is over 80 degrees and it's not raining.

4. Complete a **truth table** for the if statement that you wrote in #2 with columns for sunny, temperature > 80, raining, and go to the beach.


   
#### Boolean Game
{:.no_toc}

<div class="task" markdown="block">

🎲 Try the game below written to practice Booleans. Click on **Booleans**, look at the color and number in the block and evaluate the boolean expression to choose `true` or `false`. Then, check on Compound for an added challenge. See how high a score you can get!

<a href="https://csa-games.netlify.app/" target="_blank"><button class="btn">Boolean Game</button></a>

</div>

---

## ⭐️ Summary

- **Logical operators** ``!`` (not), ``&&`` (and), and ``||`` (or) are used with **Boolean** values.

- ``A && B`` is ``true`` if **both** ``A`` and ``B`` are ``true``.

- ``A || B`` is ``true`` if **either** ``A`` or ``B`` (or both) are ``true``.

- ``!A`` is ``true`` if ``A`` is ``false``.

- In Java, ``!`` has precedence (_is executed before_) ``&&`` which has precedence over ``||``. **Parentheses** can be used to force the order of execution in a different way.

- When the result of a logical expression using ``&&`` or ``||`` can be determined by evaluating only the first Boolean operand, the second is _not evaluated_. This is known as **short-circuit evaluation**.

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
