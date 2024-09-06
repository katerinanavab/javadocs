---
layout: notes
title: "📓1.5: Compound Assignment Operators" 
parent: "1️⃣ Primitive Types"
nav_order: 5
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 1.5](https://runestone.academy/ns/books/published/csawesome/Unit1-Getting-Started/topic-1-5-shortcutoperators.html?mode=browsing)


## Compound Assignment Operators

**Compound assignment operators** are _shortcuts_ that do a math operation and
assignment in one step. For example, ``x += 1`` adds 1 to the current value of
``x`` and assigns the result back to ``x``. It is the same as ``x = x + 1``.
This pattern is possible with any operator put in front of the ``=`` sign, as
seen below. If you need a mnemonic to remember whether the compound operators
are written like ``+=`` or ``=+``, just remember that the operation (``+``) is
done first to produce the new value which is then assigned (``=``) back to the
variable. So it's operator then equal sign: ``+=``.

Since changing the value of a variable by one is especially common, there are
two _extra concise_ operators ``++`` and ``--``, also called the plus-plus or
**increment** operator and minus-minus or **decrement** operator that set a
variable to one greater or less than its current value.

> Thus ``x++`` is even more concise way to write ``x = x + 1`` than the compound
operator ``x += 1``. You’ll see this shortcut used a lot in loops when we get to
them in Unit 4.
> 
> Similarly, ``y--`` is a more concise way to write ``y = y - 1``.
>
> These shortcuts only exist for ``+`` and ``-`` as they don’t really make sense
for other operators.

### Compound Operator Cheatsheet
Here’s a table of all the compound arithmetic operators and the extra concise
increment and decrement operators and how they relate to fully written out
assignment expressions. 


| Operator       | ``+``        | ``-``        | ``*``        | ``/``        | ``%``        |
| -------------- | ------------ | ------------ | ------------ | ------------ | ------------ |
| Written out    |``x = x + 1`` |``x = x - 1`` |``x = x * 2`` |``x = x / 2`` |``x = x % 2`` |
| Compound       |``x += 1``    |``x -= 1``    |``x *= 2``    |``x /= 2``    |``x %= 2``    |
| Extra concise  |``x++``       |``x--``       |              |              |              |

---

## ⭐️ Summary

- **Compound assignment operators** (``+=``, ``-=``, ``*=``, ``/=``, ``%=``) can be
  used in place of the assignment operator.

- The **increment** operator (``++``) and **decrement** operator (``--``) are used to
  add 1 or subtract 1 from the stored value of a variable. The new value is
  assigned to the variable.


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
