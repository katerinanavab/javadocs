---
layout: notes
title: "📓2.1: Objects" 
parent: "2️⃣ Using Objects"
nav_order: 1
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 2.1](https://runestone.academy/ns/books/published/csawesome/Unit2-Using-Objects/topic-2-1-objects-intro-turtles.html?mode=browsing) 

#### Using a GitHub Template for class notes
{:.no_toc}

<div class="setup" markdown="block">

1. Go to the public template **repository** for our class: [BWL-CS Java Template](https://github.com/BWL-CS/java-template)
2. Click the <button type="button" name="button" class="btn btn-green">Use this template</button> button above the list of files then select `Create a new repository`
3. Specify the **repository name**: `CS2-Unit-2-Notes`
4. Click <button type="button" name="button" class="btn btn-green">Create repository</button>
    > Now you have **your own personal copy** of this starter code that you can always access under the `Your repositories` section of GitHub! 
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` and wait for the environment to load, _then you're ready to code_!
7. 📝 Take notes in this Codespace during class, coding along with the instructor.

</div>


## Objects are Instances of Classes

Java is an **object-oriented programming** language. That means that one of the primary ways of organizing our programs is in terms of **objects**. 

{:.important}
**Objects** are a kind of value that combines data, and code that operates on that data, into a single _unit_. Objects are defined in Java by writing **classes** which provide a _blueprint_ for creating objects of a certain kind, describing the data and code that all **instances** of that class have.

Sometimes classes and objects are used to _model things in the real world_, such as if we made a ``Student`` class to represent students in a school. Other times classes are just ways of _organizing different parts of our programs_ that may not correspond to anything in the world outside the computer.

{:.highlight} 
But in Java all programs are built out of classes. This is why, as you saw in Unit 1, every Java program starts with ``public class``: the first thing we have to do when we write a Java program is **define at least one class**.

### What are Objects and Classes?

**Objects** are values created by **constructing** an **instance** of a **class**. This unit focuses on _using classes_, written by other coders, to create and interact with objects of a certain type. Later on, in Unit 5, you'll learn to _write your own_ classes.

When you think about making objects from a class, you can think of a class like a _blueprint_ or a cookie cutter. It is used to create the cookies (objects) and can be used to create as many cookies (objects) as you want. As a blueprint, each class defines the **attributes** its objects have (the properties or what each object knows about itself) and the **behaviors** (what each object can do). In Java code, the attributes are written as **instance variables** in the class, and the behaviors are written as **methods**.

![image](figures/cookieCutterLabelled.png)

{:.highlight}
You can also think of a class as **defining a new, custom data type**! 

Just like you use ``int`` to **declare variables** that can hold an whole number value, you can use ``Turtle`` to declare a variable whose value has to be an instance of the ``Turtle`` class.

> Just like the Java compiler will only let you do things with the values of ``int`` variables that make sense (like adding and multiplying them), it will only let you do things with values of a ``Turtle`` variable that make sense to do with turtles, namely accessing the **instance variables** and **methods** defined in the ``Turtle`` class.

The following picture has lots of cats (_objects_ of the type _Cat_). They are all different, but they share the same attributes and behaviors that make up a cat. They are all **instances** of cat with different _values_ for their attributes.

![image](figures/catsLabelled.png)

<div class="task" markdown="block">

* 💬 **Discuss with your class:** What are some attributes of cats? What are some behaviors of cats?
    > **Attributes** are often _nouns_ or _adjectives_ describing features
    >
    > **Behaviors** are often _verbs_

</div>

<div><a href="https://www.youtube.com/watch?v=64DOwDu5SVo&list=PLHqz-wcqDQIEP6p1_0wOb9l9aQ0qFijrP&ab_channel=colleenlewis" target="_blank"><button type="button" name="button" class="btn">📺 Video: Classes and Objects</button></a></div>

### Intro to Objects with Turtles

The `Turtle` class (which was written for you) is a **blueprint** for turtle objects. It defines **attributes** for graphical turtles like their `color` and `position`, and **methods** to make the turtles `move`. The Java program below creates a Turtle **object** called yertle using the Turtle **class**: 

```java
public class TurtleTest
    {
        public static void main(String[] args)
        {
            World habitat = new World(300, 300);
            Turtle yertle = new Turtle(habitat);

            yertle.forward();
            yertle.turnLeft();
            yertle.forward();

            habitat.show(true);
        }
    }
```

#### Dot Operator `.`

The **dot operator** `.` is used to call 📣 an object's method. You can think of the `.` as _commanding_ the object to do something (execute one of its methods). For example, ``yertle.forward()`` asks the turtle ``yertle`` to go ``forward``. It doesn't tell ``yertle`` how much to go forward, so it goes forward 100 pixels by default. 

The parentheses ``()`` after a method name are there in case you need to give the method **arguments** (some data) to do its job.

> _Example:_ to go forward 50 pixels instead of 100, pass the distance argument into the method: ``yertle.forward(50);`` 

#### Turtle Class Diagram

Here is a **class diagram** that shows some of the attributes and methods in the class ``Turtle``:

![image](figures/turtleUMLClassDiagram.png)

#### 💻 In-Class Activity
{:.no_toc}

<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit2-Using-Objects/topic-2-1-objects-intro-turtles.html?mode=browsing"><button type="button" name="button" class="btn">CSAwesome Topic 2.1</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: Turtle Drawing** activity in pairs.

</div>


---

## ⭐️ Summary

- A **class** defines a _new data type_ (a classification). It is the formal implementation, or _blueprint_, of the **attributes** and **behaviors** of the objects of that class.

- An **object** is a specific **instance** of a class with defined attributes. Objects are declared as variables of a class type.

- An **attribute** or **instance variable** is data the object knows about itself.
    - _Example:_ a Turtle object knows the direction it is facing or its color.

- A **behavior** or **method** is something that an object can do.
    - _Example:_ a Turtle object can go forward 100 pixels.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
