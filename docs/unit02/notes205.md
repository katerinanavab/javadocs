---
layout: notes
title: "📓2.5: Methods that Return Values" 
parent: "2️⃣ Using Objects"
nav_order: 5
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 2.5](https://runestone.academy/ns/books/published/csawesome/Unit2-Using-Objects/topic-2-5-methods-return.html?mode=browsing) 

<div class="setup" markdown="block">

📝 Take notes in a **Codespace** during class, coding along with the instructor.

1. Go to GitHub and click on your picture in the _TOP RIGHT_ corner
2. Select `Your repositories`
3. Open `CS2-Unit-2-Notes`
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` (unless you already have one listed there), wait for the environment to load, _then you're ready to code_!

</div>

## Methods that Return Values

All the methods on ``Turtle`` that we’ve discussed so far have had a ``void``
return type. Such methods are sometimes called **void methods**. 

⬛️ Because a ``void`` method _does NOT return any value_, the only point of calling one is
because it *does something* that can be observed by the user or by other code—it
**changes the state** of the object or maybe **causes something to happen** like drawing
a line on the screen. Or both. 
> 🪄 These things they do are sometimes called **effects**.

{:.important}
Methods with a **return** type of anything other than ``void`` are called **non-void** methods. These methods **return** a value (output) that the code
calling the method can use. 
> And because methods are called on an **object**, these methods can be used to return values that tell us things about an object’s
_internal state_.

Most methods are of one kind or the other: either a **void** method which is called for some effect or a **non-void** method that is called to compute a value
but otherwise has no effect. 

{:.highlight}
To put it another way, **void** methods *do things* while **non-void** methods *produce values*.

### Accessors / Getters

A simple kind of method that returns a value is what is formally called an
**accessor** because it _accesses a value_ in an object. 
* In the real world everyone calls them **getters**.
* A getter is a method that takes no arguments and has a non-``void`` return type.
* In Java they are almost always named something that starts with ``get``, and they usually just return the value of one
of the object’s **instance variables**. 
> For example, the ``Turtle`` class has several getters, ``getWidth`` and ``getHeight`` which return the width and the height of a ``Turtle`` object and ``getXPos`` and ``getYPos`` which return the x and y values of the `Turtle`’s position.

Here are some examples of using getters on the ``Turtle`` object ``yertle``.

```java
Turtle yertle = new Turtle(world);
int width = yertle.getWidth();
int height = yertle.getHeight();
System.out.println("Yertle's width is: " + width);
System.out.println("Yertle's height is: " + height);
System.out.println("Yertle's x position is: " + yertle.getXPos() );
System.out.println("Yertle's y position is: " + yertle.getYPos() );
```

{:.highlight}
⚠️ A common mistake is forgetting to _do something_ with the **value returned** from a method. When you call a method that returns a value, you should do something with that output, like **assigning it to a variable**, using it in an **expression**, or **printing it out**.

### Methods with Arguments and a Return Value

Since getters take no arguments, all they can do is return a value based on the current state of the object. But often it’s useful to have methods that **compute values** based on both the current state of the object and some arguments. 

For example, while we could use a ``Turtle``’s ``getXPos`` and ``getYPos``
getters and some math to figure out how far away a ``Turtle`` is from any given point, if that’s a thing we need to do in a lot of programs using ``Turtle``, it might be nice to be able to ask a ``Turtle`` directly for its distance from a given point. 

And indeed, the ``Turtle`` class has a method called ``getDistance`` that takes two ``int`` arguments representing an `x` value and a `y` value and returns the distance between the ``Turtle``’s current position and that `x,y` point. This is _not a getter_ because it doesn’t just get an existing value; it **computes** a new value based on the arguments it is passed as well as the state of the ``Turtle``.

{:.highlight}
Methods that take arguments and return values are somewhat like mathematical functions. Given some **input**, they return **output**. 

> (Mathematicians expect that a function always returns the same value, given the same arguments. So they would not consider something like ``getDistance(x, y)`` a true function since its return value also depends on the current position of the ``Turtle``. But we’re doing programming, not math.)

![image](figures/function.png)


#### 💻 In-Class Activity
{:.no_toc}

<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit2-Using-Objects/topic-2-5-methods-return.html?mode=browsing"><button type="button" name="button" class="btn">CSAwesome Topic 2.5</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: Turtle Distances** activity in pairs.

</div>

---

## ⭐️ Summary

- **Non-void methods** are methods that _return values_ (provide output).

- Non-void methods typically do not have other effects, and are called purely to generate the
  value they return.

- It is up to the caller of a non-void method to _do something_ with the return
  value, such as **assigning** it to a variable or using it as part of an
  **expression**.

- The **value returned** by a method has to match the **declared return type** of the
  method. Thus it can only be used where a value of that type is allowed, such
  as being assigned to a variable of that type. 

<br>

<div class="warn" markdown="block">

🛑 When class ends, don't forget to **SAVE YOUR WORK**!

1. Navigate to the `Source Control` menu on the _LEFT_ sidebar
2. Click the <button type="button" name="button" class="btn btn-green">commit changes</button> button on the _LEFT_ menu
3. Type a brief **commit message** at the top of the file that opens, for example: `updated Main.java`
4. Click the small `✔️` **checkmark** in the _TOP RIGHT_ corner
5. Click the <button type="button" name="button" class="btn btn-green">sync changes</button> button on the _LEFT_ menu
6. _Finally you can close your Codespace!_

</div>

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
