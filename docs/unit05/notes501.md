---
layout: notes
title: "📓5.1: Classes & Objects" 
parent: "5️⃣ Writing Classes"
nav_order: 1
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 5.1](https://runestone.academy/ns/books/published/csawesome/Unit5-Writing-Classes/topic-5-1-parts-of-class.html?mode=browsing) 

#### Using a GitHub Template for class notes
{:.no_toc}

<div class="setup" markdown="block">

1. Go to the public template **repository** for our class: [BWL-CS Java Template](https://github.com/BWL-CS/java-template)
2. Click the <button type="button" name="button" class="btn btn-green">Use this template</button> button above the list of files then select `Create a new repository`
3. Specify the **repository name**: `CS2-Unit-5-Notes`
4. Click <button type="button" name="button" class="btn btn-green">Create repository</button>
    > Now you have **your own personal copy** of this starter code that you can always access under the `Your repositories` section of GitHub! 
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` and wait for the environment to load, _then you're ready to code_!
7. 📝 Take notes in this Codespace during class, coding along with the instructor.

</div>

---

## Anatomy of a Java Class

In Unit 2, we learned to use **classes** and **objects** that are built-in to
Java or written by other programmers. In this unit, you will learn to write your
own classes and make your own objects!

Remember that a **class** in Java defines a _blueprint_ for creating objects. When
you create **objects**, you create new **instances** of that class and what you
can do with those instances is determined by what methods are defined in the
class.
> For example in Unit 2, we created ``yertle`` and ``myrtle``, 2 ``Turtle``
variables and assigned them references to objects created from the class
``Turtle`` and we used instances of Java’s ``String`` class to assign values to
different ``String`` variables.

Watch this short video to review the vocabulary of object-oriented programming:
<a href="https://www.youtube.com/watch?v=LfSaSANJPLg" target="_blank"><button class="btn">📺 VIDEO</button></a>

### Creating a Class

Most classes you write will have the keyword ``public`` before them though it is
not required. The **class definition** itself always starts with the **keyword** ``class``
followed by the **name** of the class. Then the rest of the class, called the **body**,
is defined inside a pair of ``{ }``s.

Since we’re talking about anatomy, let’s create a class called ``Person``.
Classes are almost always named with capitalized names though this is a matter
of style, not a rule of the language. Here is the basic skeleton of a ``Person``
class:

```java
public class Person
{
    // define class here - also called the “body” of the class

}
```

You can create **instances** of the ``Person`` class with ``new`` as in ``new
Person()`` And you can declare variables that can hold a reference to a
``Person`` object with ``Person variableName``. Put it altogether to **declare some variables** and **initialize** each one with a reference to a new ``Person`` object as shown here:

```java
// Create OBJECTS - instances of the class
Person ada = new Person();
Person charles = new Person();
```

So what makes up the **body** of the class—the stuff between the ``{}``s?

{.highlight}
Remember that `objects` have both _attributes_ and _behaviors_. These correspond to
**instance variables** and **methods** in the `class` definition.

The first things we define in a class are usually the **instance variables**. They
are called that because each instance of the class (each object) has its own set
of variables that aren’t shared with other instances. 
> This is what allowed ``yertle`` and ``myrtle`` from Unit 2 to be at different positions at the same
time; they each had their own x position and y position instance variables.

The next thing we define in a class is usually its **constructors**. We’ll talk
about writing constructors in more detail in the next section but a
constructor’s job is to initialize the instance variables when the object is
created. Usually that will mean they need to take arguments. 

The real meat of a class is in the **methods** which define the _behaviors_ of the
objects of that class. 
> Recall from Unit 2 that most methods either do things
(like the ``Turtle`` methods that moved the turtle on the screen) or return
values like the ``getXPos`` and ``getYPos`` on ``Turtle``.

The methods of the class **share access to the object’s instance variables** and
when a method is called on an object it uses the instance variables for that
object. 
> For example in the ``Turtle`` class the ``forward`` method changes an
instance variable ``xPos``. When you call ``forward`` on ``yertle`` it changes
``xPos`` on the ``yertle`` object and when you call it on ``myrtle`` it changes
the ``xPos`` on the ``myrtle`` object.

<div class="imp" markdown="block">
    
_Putting it all together, the three main anatomical features of a class are:_

1. The **instance variables** which hold values (_attributes_) associated with each object
2. The **constructors** whose job is to initialize the instance variables for an object
3. The **methods** who contain the code that gives the objects their _behavior_ and which
can use the instance variables defined in the class

```java
public class Person
{
    // 1. INSTANCE VARIABLES

    // 2. CONSTRUCTORS

    // 3. METHODS

}
```

</div>

> ADDITIONALLY, any Java class can have a ``main`` method which can be used to run that class as a
program either to **test** that one class, or sometimes act as the **entry point** to a whole
program made up of many classes and objects.

Now that we know what the skeleton of a class looks like and the elements that
make up the body of the class, we’re ready to create our own class! Let’s start
with a look at how to design a class such as ``Person``.

{.highlight}
One important question we have to ask when designing a class is, **what data does
it represent**? In this case we can ask, what would we want to _know_ about a
person? Our answer will depend on what problem we are trying to solve. 

> In one program, perhaps an address book, we might want to know the person's name and
phone number and email. In another program, such as a medical application, we
might need to know their vital signs such as their blood pressure, temperature,
and pulse rate.

### Instance Variables

### Methods

### Object-Oriented Design

So far we’ve just talked about designing one class. In **object-oriented
design** (OOD), programmers often start by deciding which **classes** are needed to
solve a problem, and then figure out the **data** and **methods** in each class.

{:.highlight}
When you are given a problem specification, you can identify **classes** you’ll need
by looking for the _nouns_ in the specification. 

> For instance, the specification for the turtle graphics system from Unit 2 probably contained a
sentence that said something like, _“there are turtles that can exist on a
2-dimensional world and can draw lines by moving around the world”_. The main
nouns in that description are “turtle” and “world” and indeed the classes in the
system are ``Turtle`` and ``World``.
> (The one noun that was not turned into a
class was “line”. Do you think it would have made sense to create a ``Line``
class? Why or why not?)

Once you’ve determined the classes you need, then you can go through the process
we described above to design the individual classes. 

{.highlight} Note that you can often identify **methods** that should exist on classes by looking for _verbs_ in the
specification, like “move”.

#### Drawing Class Diagrams

Sometimes it’s useful, when designing a complex system with lots of classes, to
make diagrams of the classes that show you at a glance what instance variables
and methods they have. Often these can just be sketches in your notebook or on a
whiteboard but there are also more formal systems such as the Unified Modeling
Language (UML) for drawing these diagrams.

{.important}
Here is a [tutorial on class diagrams](https://medium.com/@smagid_allThings/uml-class-diagrams-tutorial-step-by-step-520fd83b300b) that explains it in more detail if you are curious (_drawing class diagrams is not tested on the AP CSA exam_). If you want to draw your own, [app diagrams](https://app.diagrams.net/) or [Creately.com](https://creately.com) are good free online drawing tools for UML class diagrams.

For example, here is a UML class diagram for the ``Turtle`` class. The ``-`` in
front of the attributes indicate that they are private, and the ``+`` in front
of the methods indicate that they are public. 

![image](Figures/turtleUMLClassDiagram.png)

#### 🧠 Check Your Understanding
{:.no_toc}

<div class="task" markdown="block">
    
Say you wanted to make a computer game from a board game that you are playing. Think about what objects are in the game. For example, here is the description for **Monopoly** (trademark Hasbro games):
> "Buy, sell, dream and scheme your way to riches. Players buy, sell and trade to win. Build houses and hotels on your properties and bankrupt your opponents to win it all. Chance and Community Chest cards can change everything." 

What **classes** would you need to create a computer version of this game? (Remember to look for the _nouns_). Take one of the classes you listed, and try to come up with 2 pieces of _data_ in that class that will be the **instance variables**.

</div>

#### 💻 In-Class Activity: Riddle Class
{:.no_toc}


<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit5-Writing-Classes/topic-5-1-parts-of-class.html?mode=browsing"><button type="button" name="button" class="btn">CSAwesome Topic 5.1</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: Riddle Class** activity in pairs.

</div>

---

## ⭐️ Summary

- Programmers use code to represent a physical object or nonphysical concept,
  real or imagined, by defining a class based on the attributes and/or behaviors
  of the object or concept.

- **Instance Variables** define the attributes or data needed for objects, and
  **methods** define the behaviors or functions of the object.

- **Data encapsulation** is a technique in which the implementation details of a
  class are kept hidden from the user. The data is kept private with access only
  through the public methods that can act on the data in the class.

- The keywords ``public`` and ``private`` affect the access of classes, data,
  constructors, and methods.

- The keyword ``private`` restricts access to the declaring class, while the
  keyword ``public`` allows access from classes outside the declaring class.

- Instance variables are encapsulated by using the ``private`` **access
  modifier**.

- Methods can be ``public`` or ``private``. The set of ``public`` methods define
  what other classes can do with an instance of a class.


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
