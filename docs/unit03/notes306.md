---
layout: notes
title: "📓3.6: DeMorgan's Laws" 
parent: "3️⃣ Conditionals"
nav_order: 6
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 3.6](https://runestone.academy/ns/books/published/csawesome/Unit3-If-Statements/topic-3-6-DeMorgan.html?mode=browsing) 

<div class="setup" markdown="block">

📝 Take notes in a **Codespace** during class, coding along with the instructor.

1. Go to GitHub and click on your picture in the _TOP RIGHT_ corner
2. Select `Your repositories`
3. Open `CS2-Unit-3-Notes`
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` (unless you already have one listed there), wait for the environment to load, _then you're ready to code_!

</div>


## Equivalent Boolean Expressions

What if you heard a rumor about a senior at your high school? And then you heard that the rumor wasn't true - it wasn't a senior at your high school. Which part of "a senior at your high school" wasn't true? Maybe they weren't a senior? Or maybe they didn't go to your high school? You could write this as a logic statement like below using **negation** (``!``) and the **and** (``&&``) operator since both parts have to be true for the whole statement to be true.

```java
a = "senior"
b = "at our high school"

!(a && b)

// This means it is not true that (a) it is a senior
// and (b) someone at our high school.
```

### De Morgan's Laws

De Morgan's Laws were developed by Augustus De Morgan in the 1800s.  They show how to simplify the negation of a complex boolean expression, which is when there are multiple expressions joined by an **and** (``&&``) or **or** (``||``), such as ``(x < 3) && (y > 2)``. When you negate one of these complex expressions, you can simplify it by flipping the operators and end up with an equivalent expression. De Morgan's Laws state the following equivalencies. Here's an easy way to remember De Morgan's Laws: **move the NOT inside, AND becomes OR** and **move the NOT inside, OR becomes AND**.

![image](Figures/demorgan.png)

In Java, De Morgan's Laws are written with the following operators:
-  ``!(a && b)`` is equivalent to ``!a || !b``
-  ``!(a || b)`` is equivalent to ``!a && !b``

Going back to our example above, `not(a senior AND at our high school)` is equivalent to `not(a senior) OR not(at our high school)` using De Morgan's Laws:

```
a = "senior"
b = "at our high school"

!(a && b) is equivalent to !a || !b
```
        

You can also simplify negated boolean expressions that have relational operators like ``<``, ``>``, ``==``. You can move the negation inside the parentheses by flipping the relational operator to its opposite sign. For example, not (c equals d) is the same as saying c does not equal d.  An easy way to remember this is **To move the NOT, flip the sign**. Notice that ``==`` becomes ``!=``, but ``<`` becomes ``>=``,  ``>`` becomes ``<=``, ``<=`` becomes ``>``, and ``>=`` becomes ``<`` where the sign is flipped and an equal sign may also be added or removed.

  - ``!(c == d)`` is equivalent to ``c != d``
  - ``!(c != d)`` is equivalent to ``c == d``
  - ``!(c < d)`` is equivalent to ``c >= d``
  - ``!(c > d)`` is equivalent to ``c <= d``
  - ``!(c <= d)`` is equivalent to ``c > d``
  - ``!(c >= d)`` is equivalent to ``c < d``

### Truth Tables

Although you do not have to memorize De Morgan's Laws for the CSA Exam, you should be able to show that two boolean expressions are equivalent. One way to do this is by using truth tables. 

For example, we can show that ``!(a && b)`` is equivalent to ``!a || !b`` by constructing the truth table below and seeing that they give identical results for the 2 expressions (the last 2 columns in the table below are identical!).

| a     | b     | `!(a && b)` | `!a \|\| !b` |
|-------|-------|-----------|----------|
| true  | true  | false     | false    |
| false | true  | true      | true     |
| true  | false | true      | true     |
| false | false | true      | true     |

### Simplifying Boolean Expressions

Often, you can simplify boolean expressions to create equivalent expressions. For example, applying De Morgan's Laws to ``!(x < 3 && y > 2)`` yields ``!(x < 3) || !(y > 2)`` as seen in the figure below. This can then be simplified further by flipping the relational operators to remove the not.  So, ``!(x < 3) || !(y > 2)`` is simplified to ``(x >= 3 || y <= 2)`` where the relational operators are flipped and the negation is removed. These two simplification steps are seen below.

![image](Figures/demorganex.png)


---

## ⭐️ Summary

- **De Morgan’s Laws** can be applied to Boolean expressions to create equivalent ones:

  - ``!(a && b)`` is equivalent to ``!a || !b``
  - ``!(a || b)`` is equivalent to ``!a && !b``

- A negated expression with a relational operator can be simplified by _flipping the relational operator_ to its opposite sign.

  - ``!(c == d)`` is equivalent to ``c != d``
  - ``!(c != d)`` is equivalent to ``c == d``
  - ``!(c < d)`` is equivalent to ``c >= d``
  - ``!(c > d)`` is equivalent to ``c <= d``
  - ``!(c <= d)`` is equivalent to ``c > d``
  - ``!(c >= d)`` is equivalent to ``c < d``

- Truth tables can be used to prove that 2 Boolean expressions are identical.

- Equivalent Boolean expressions will evaluate to the same value in all cases.


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
