---
layout: notes
title: "📓1.6: Casting" 
parent: "1️⃣ Primitive Types"
nav_order: 6
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 1.6](https://runestone.academy/ns/books/published/csawesome/Unit1-Getting-Started/topic-1-6-casting.html?mode=browsing)


## Casting & Ranges of Values

In Java, **type casting** is used to convert values from one type to another. By
**casting** we don't mean something to do with fishing, but it is a similar idea
to casting a bronze, without needing to heat anything to 913 degrees Celsius.
But like molten bronze is reshaped by melting it and pouring it into a mold, our
data is reshaped via a **cast** operator. In Java when you cast you are changing
the "shape" (or type) of the value.

![image](bronze-casting.jpg)

The **cast operator**, which looks like ``(int)`` and ``(double)`` placed before
any **expression** (a literal, a number, a variable, or more complex expression in
parentheses) produces a **value** of the given type by _converting_ the value of the
original expression to the new type.

> For example, ``(double) 1 / 3`` will evaluate to a ``double`` value instead of an
``int``. 

<div class="task" markdown="1">

1. Run this code to find how Java handles division and what casting can do
to the results. Notice what happens when you divide an ``int`` by an ``int`` or
an ``int`` by a ``double`` or an ``int`` cast to a ``double`` divided by an
``int``.

```java
System.out.println(3 / 4);          // int divided by int
System.out.println(3.0 / 4);        // double divided by int
System.out.println(3 / 4.0);        // int divided by double
System.out.println((double) 3 / 4); // int cast to double, divided by int
System.out.println((int) 3.0 / 4);  // double cast to int, divided by int
```

2. What happens when you divide an int by an int or with a double operand or with the type cast (double) or (int) on one of the operands? Add another line that divides 5 by 2 using a `(double)` cast. What is the result?

</div>

### Conversions in Calculations

When Java divides two ``int``\ s, it produces an ``int`` result by truncating
the actual mathematical result, removing anything after the decimal point. Thus
``9 / 10`` evaluates to ``0``, not ``0.9``. It also does not evaluate to ``1``;
truncating is not the same as rounding!

But in any expression involving a ``double``, the ``double`` is “contagious” and
will cause the value of that expression to also be a ``double``. Thus the
expression ``9.0 / 10`` is evaluated as if it had been written ``9.0 / 10.0`` and
produces the ``double`` value ``0.9``.

> Casting an ``int`` to ``double``, as shown in the code above, produces a
``double`` value which will then causes any expression it is part of to produce
a ``double``. This is especially useful when you have ``int`` variables that
you want to do non-integer division with.

{:.highlight}
A conversion from ``int`` to ``double`` is called a **widening conversion**
because a ``double`` can represent any ``int`` value but not vice versa; thus a
``double`` is considered a wider data type than an ``int``.

### Rounding by Casting

Values of type ``double`` in the range that can be represented by an ``int`` can
be rounded to the nearest ``int`` by adding or subtracting 0.5 and then casting
the result with ``(int)``:

```java
double number;    // positive value from somewhere
double negNumber; // negative value from somewhere

int nearestInt = (int)(number + 0.5);
int nearestNegInt = (int)(negNumber – 0.5);
```

> For example, if you divide ``7.0 / 4.0`` you get ``1.75``. If you cast that to
an ``int``, it will be truncated to ``1``.
> 
> However if we want to round a ``double`` rather than truncating it, adding ``0.5`` will produce a number that
is above the next integer value if the decimal part is greater than ``0.5``, as
it is here. Then casting *that* value to an ``int`` will truncate down.

### Precision

What happens to repeating decimal numbers like 3.333333...?  Java limits the number of digits you can save for any ``double`` number to about 14-15 digits. You should be aware that the accuracy of any calculation on a computer is limited by the fact that computers can only hold a limited number of digits.

For example, int values are stored in 4 bytes of memory. There is an
``Integer.MAX_VALUE`` defined as 2147483647 and an ``Integer.MIN_VALUE`` defined
as -2147483648. If you try to store any number larger or smaller than these
numbers in an int variable, it will result in an **integer overflow** where an
incorrect value could be stored. Try it below.

---

## ⭐️ Summary

Summary
-------------------

- **Type casting** is used to _convert_ values from one type to another.

- The **casting operators** ``(int)`` and ``(double)`` can be used to create a
  temporary value converted to a different data type.

- Casting a ``double`` value to an ``int`` causes the digits to the right of the
  decimal point to be **truncated** (cut off and thrown away).

- In expressions involving ``double``s, the ``double`` values are contagious,
  causing ``int``s in the expression to be **automatically converted** to the
  equivalent ``double`` value so the result of the expression can be computed as
  a ``double``.

- Values of type ``double`` can be rounded to the **nearest integer** by `(int)(x +
  0.5)` or `(int)(x – 0.5)` for negative numbers.

- Integer values in Java are represented by values of type ``int``, which are
  stored using a finite amount (4 bytes) of **memory**. Therefore, an int value must
  be in the range from ``Integer.MIN_VALUE`` to ``Integer.MAX_VALUE``,
  inclusive.

- If an expression would evaluate to an `int` value outside of the allowed range,
  an **integer overflow** occurs. This could result in an incorrect value within the
  allowed range.
  
---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
