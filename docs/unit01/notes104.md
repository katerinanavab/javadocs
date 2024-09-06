---
layout: notes
title: "📓1.4: Expressions & Assignment Statements" 
parent: "1️⃣ Primitive Types"
nav_order: 4
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 1.4](https://runestone.academy/ns/books/published/csawesome/Unit1-Getting-Started/topic-1-4-assignment.html?mode=browsing)


## Assignment Statements

**Assignment statements** initialize or change the value stored in a variable using the assignment operator ``=``.  An assignment statement always has a single variable on the left hand side. The value of the **expression** (which can contain math operators and other variables) on the right of the ``=`` sign is _stored_ in the variable on the left.

![image](assignment.png)

> Instead of saying "equals" for the `=` in an assignment statement, say "gets" or "is assigned" to remember that the **variable** gets or is assigned the **value** on the right.

### Increment: Add 1 to a Variable

If you use a variable to keep score, you would probably **increment** it (add one to the current value) whenever score should go up. You can do this by setting the
variable to the current value of the variable plus one (``score = score + 1``). 
 
> The formula would look strange in math class, but it
makes sense in coding because it is _assigning_ a new value to the variable on the
left that comes from _evaluating_ the arithmetic expression on the right. So, the
score variable is set to the previous value of score plus 1.

---

## Operators

Java uses the standard mathematical operators for **addition** (``+``), **subtraction**
(``-``), and **division** (``/``). The **multiplication** operator is written as ``*``, as
it is in most programming languages. You will learn how to use the  ``Math.pow()`` method to do **exponents** in Unit 2.

**Arithmetic expressions** can be of type ``int`` or ``double``. An arithmetic
expression consisting only of ``int`` values will evaluate to an ``int`` value.
An arithmetic expression that uses at least one ``double`` value will evaluate
to a ``double`` value.

### Testing Equality with `==`

Java uses the operator ``==`` to test if the value on the left is equal to the
value on the right and ``!=`` to test if two items are not equal. Don't get one
equal sign ``=`` confused with two equal signs ``==``. They mean very different
things in Java. 
* One equal sign is used to _assign_ a value to a variable.
* Two equal signs are used to _test_ a variable to see if it is a certain value and that returns `true` or `false`.

<div class="task" markdown="1">

Run the statements below to see all the **operators** in action. 

> Do all of those operators do what you expected? What about `2 / 3`? Isn't it surprising that it prints `0`?

```java
System.out.println(2 + 3);
System.out.println(2 - 3);
System.out.println(2 * 3);
System.out.println(2 / 3);

// == is to test while = is to assign
System.out.println(2 == 3);
System.out.println(2 != 3);
```

</div>

{:.warning}
When Java sees you doing **integer division** (or any operation with integers) it assumes you want an `int` result too, so it _throws away anything after the decimal_ point in the answer. This is called **truncating**. If you need a `double` answer, you should make at least one of the values in the expression a `double` like `2.0`.

{:.highlight}
With division, another thing to watch out for is **dividing by 0**. An attempt to divide an integer by zero will result in an `ArithmeticException` error message.

### Operator Precedence

Operators can be used to create **compound expressions** with more than one operator. You can either use a literal value which is a fixed value like `2`, or variables in them.  When compound expressions are evaluated, **operator precedence** rules are used, just like when we do math (remember PEMDAS?), so that ``*``, ``/``, and ``%`` are done before ``+`` and ``-``. 
> However, anything in parentheses is done first. It doesn't hurt to put in extra parentheses if you are unsure as to what will be done first or just to make it more clear.


### The Remainder Operator `%`

The operator ``%`` in Java is the **remainder** operator. Like the other
arithmetic operators it takes two operands. Mathematically it **returns** the
remainder after dividing the first number by the second, using **truncating** integer division. 

> _Example:_ ``5 % 2`` evaluates to 1 since 2 goes into 5 two times
with a remainder of 1.

---
## ⭐️ Summary

- Arithmetic **expressions** include expressions of type ``int`` and ``double``.

- The arithmetic **operators** consist of ``+``, ``-``, ``*`` , ``/``, and ``%``
  also known as addition, subtraction, multiplication, division, and remainder.

- An arithmetic operation that uses two ``int`` values will evaluate to an
  ``int`` value. With integer division, any decimal part in the result will be
  **truncated**.

- An arithmetic operation that uses at least one ``double`` value will evaluate
  to a ``double`` value.

- Operators can be used to construct **compound expressions**.

- During evaluation, operands are associated with operators according to **operator precedence** to determine how they are grouped.
  - ``*``, ``/``,  ``%`` have precedence over ``+`` and ``-``, unless parentheses are used to group those)

- An attempt to divide an integer by zero will result in an ``ArithmeticException``.

- The assignment operator (``=``) allows a program to initialize or change the
  value stored in a variable. The value of the expression on the right is stored
  in the variable on the left.

- During program execution, **expressions** are _evaluated_ to produce a single value.

- The value of an expression has a **type** based on the types of the values and
  operators used in the expression.


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
