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

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
