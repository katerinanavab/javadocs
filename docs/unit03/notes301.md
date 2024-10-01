---
layout: notes
title: "📓3.1: Booleans" 
parent: "3️⃣ Conditionals"
nav_order: 1
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 3.1](https://runestone.academy/ns/books/published/csawesome/Unit3-If-Statements/topic-3-1-booleans.html?mode=browsing) 

#### Using a GitHub Template for class notes
{:.no_toc}

<div class="setup" markdown="block">

1. Go to the public template **repository** for our class: [BWL-CS Java Template](https://github.com/BWL-CS/java-template)
2. Click the <button type="button" name="button" class="btn btn-green">Use this template</button> button above the list of files then select `Create a new repository`
3. Specify the **repository name**: `CS2-Unit-3-Notes`
4. Click <button type="button" name="button" class="btn btn-green">Create repository</button>
    > Now you have **your own personal copy** of this starter code that you can always access under the `Your repositories` section of GitHub! 
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` and wait for the environment to load, _then you're ready to code_!
7. 📝 Take notes in this Codespace during class, coding along with the instructor.

</div>


## Boolean Expressions

**Boolean** variables or expressions can only have **true** or **false** values.

### Testing Equality `==`

The operators ``==`` and ``!=`` (not equal) can be used to compare values. They return true or false boolean values.

{:.important}
One ``=`` sign changes the value of a variable. Two ``==`` equal signs are used to test if a variable holds a certain value, without changing its value!

Watch the following video which shows what happens in memory as primitive types like ``int`` and reference types like ``Dog`` are compared with ``==`` in a physical model of Java memory:

<a href="https://www.youtube.com/watch?v=bO9bejT0jwE&list=PLHqz-wcqDQIEP6p1_0wOb9l9aQ0qFijrP&ab_channel=colleenlewis" target="_blank"><button type="button" name="button" class="btn btn-purple">📺 Video: Testing Equality</button></a>

<div class="task" markdown="block">

What will the code below print out? Try to guess before you run it! Note that 1 equal sign (``=``) is used for assigning a value and 2 equal signs (``==``) for testing values.

```java
int age = 15;
int year = 14;
// Will this print true or false?
System.out.println(age == year);
year = 15;
// Will this print true or false?
System.out.println(age == year);
// Will this print true or false?
System.out.println(age != year);
```
</div>

We can also use ``==`` or ``!=`` to test if two **reference** values, like ``Turtle`` and ``String`` objects, refer to the same **object**. 

In the figure below, we are creating two separate ``Turtle`` objects called ``juan`` and ``mia``. _They do NOT refer to same object or turtle!_ Then, we create a reference variable called ``friend`` that is set to ``mia``. The turtle ``mia`` will have two ways (**references** or **aliases**) to name her -- she's both ``mia`` and ``friend``, and these variables refer to the same object (same ``Turtle``) in memory. If two reference  variables refer to the same object like the turtle on the right in the image below, the test with ``==`` will return true which you can see in the code below.

![image](Figures/turtleEquality.png)

### Relational Operators `<`, `>`

The **Relational Operators** below in Java are used to compare numeric values or arithmetic expressions. Although some programming languages allow using relational operators like ``<`` to compare strings, Java only uses these operators for numbers, and uses the methods ``compareTo`` and ``equals`` for comparing ``String`` values.

| ``<``  | Less than |
| ``>``  | Greater than |
| ``<=`` | Less than or equal to |
| ``>=`` | Greater than or equal to |
| ``==`` |  Equals |
| ``!=`` | Does not equal |

If you have trouble telling ``<`` and ``>`` apart, think of ``<`` and ``>`` as
arrows where the pointy end should _point to the smaller value_. If ``<`` (less
than) points towards a smaller number on the left, then it evaluates to
``true``. On the other hand a ``>`` (greater than) expression will be ``true``
only if the smaller number is on the right hand side. 

Or maybe you prefer the “hungry alligator” mnemonic beloved by elementary school teachers—think of ``<`` and ``>`` as the mouths of hungry alligators which always want to _eat the bigger number_; a ``<`` or ``>`` expression is only ``true`` if the alligator is in fact about to eat the bigger number.

{:.highlight}
To remember the correct order of the two characters in ``<=`` and ``>=``, just
write them in the same order you would say them in English: “less than or equal
to” not “equal to or less than”.

#### Relational Operators Game
{:.no_toc}

<div class="task" markdown="block">

Try the game below written by AP CSA teacher Chandan Sarkar. Try the game below to practice. Click on _Relationals_, evaluate the relational expression and click on **None**, **All**, or the **numbers** that make the expression `true`. Check on _Compound_ for an added challenge. We encourage you to work in pairs and see how high a score you can get.

<a href="https://csa-games.netlify.app/" target="_blank"><button class="btn">Relational Operators Game</button></a>

</div>

---

## ⭐️ Summary

- Primitive values and reference values can be compared using **relational operators** (i.e., ``==`` and ``!=``) in Java.
- Arithmetic expression values can be compared using **relational operators** (i.e., ``<``, ``>``, ``<=``, ``>=``) in Java.
- An **expression** involving relational operators _evaluates_ to a ``boolean`` value of either ``true`` or ``false``.


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
