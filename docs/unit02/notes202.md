---
layout: notes
title: "📓2.2: Constructors" 
parent: "2️⃣ Using Objects"
nav_order: 2
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 2.2](https://runestone.academy/ns/books/published/csawesome/Unit2-Using-Objects/topic-2-2-constructors.html?mode=browsing) 

<div class="setup" markdown="block">

📝 Take notes in a **Codespace** during class, coding along with the instructor.

1. Go to GitHub and click on your picture in the _TOP RIGHT_ corner
2. Select `Your repositories`
3. Open `CS2-Unit-2-Notes`
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` (unless you already have one listed there), wait for the environment to load, _then you're ready to code_!

</div>

## Constructors: Creating and Initializing Objects

A Java class defines what objects of the class know (attributes) and what they can do (behaviors).  Each class has **constructors** like ``World()`` and ``Turtle(habitat)`` which are used to initialize the attributes in a newly created object.

A new object is created with the ``new`` keyword followed by the class name (``new Class()``).  When this code executes, it creates a new object of the specified class and calls a constructor, which has the same name as the class.  For example, ``new World()`` creates and initializes a new object of the ``World`` class, and ``new Turtle(habitat)`` creates and initializes a new ``Turtle`` object in the World habitat.

<div class="imp" markdown="block">
    
🏗️ Syntax pattern to create a `new` **object** and call a **constructor**:

```java
ClassName variableName = new ClassName(parameters);
```

</div>

**Examples:**
```java
World habitat = new World();    // create a new World object
Turtle t = new Turtle(habitat); // create a new Turtle object
```

### Overloading Constructors

There can be _more than one constructor_ defined in a class. This is called **overloading** the constructor. 

{:.important}
Constructors are **overloaded** when there are multiple constructors, but the constructors have different _signatures_. They can differ in the number, type, and/or order of parameters (_input_). Think of overloading constructors as providing different options to "set up" an object.

* There is usually a constructor that has no parameters (nothing inside the parentheses following the name of the constructor) like the ``World()`` constructor above. This is also called the **no-argument constructor**. The **no-argument** constructor usually sets the attributes of the object to default values.

* There can also be other constructors that take parameters like the ``Turtle(habitat)`` constructor call above. A **parameter** (also called **actual parameter** or **argument**) is a value that is passed into a constructor. It can be used to initialize the attribute of an object.

The ``World`` class actually has **2 constructors**: one doesn't take any parameters, and one takes the world's `width` and `height`.

![image](figures/worldConstructors.png)

### The `World` Class Constructors
{:.no_toc}

The constructor that doesn't take any parameters, ``World()``, creates a graphical window with 640x480 pixels. The ``World(int width, int height)`` constructor takes two integer parameters, and initializes the ``World`` object's width and height to them, for example ``new World(300,400)`` creates a 300x400 pixel world.

```java
World world1 = new World(); // creates a 640x480 world
World world2 = new World(300,400); // creates a 300x400 world
```

{:.highlight}
🗺️ The Turtle world does not use the Cartesian coordinate system with `(0,0)` in in the middle the screen. Instead: `(0,0)` is at the **top left corner** of the screen, `x` increases to the right, and `y` increases towards the bottom of the screen.

### The `Turtle` Class Constructors
{:.no_toc}

The ``Turtle`` class also has multiple constructors, although it always requires a world as a parameter in order to have a place to draw the turtle. The default location for the turtle is right in the middle of the world.

There is another ``Turtle`` constructor that places the turtle at a certain (x,y) location in the world, for example at the coordinate (50, 100) below.

```java
Turtle t1 = new Turtle(world1);
Turtle t2 = new Turtle(50, 100, world1);
```

{:.highlight}
Notice that the **order** of the parameters matter. The ``Turtle`` constructor takes ``(x,y,world)`` as parameters in that order. 
> If you mix up the order of the parameters it will cause an error, because the parameters will not be the data types that it expects. This is one reason why programming languages have data types -- to allow for error-checking.

### Object Variables and References

You can also declare an **object variable** and initialize it to **null** (``Turtle t1 = null;``). An object variable holds a **reference** to an object.  A **reference** is a way to find the object in memory. It is like a tracking number that you can use to track the location of a package.

<a href="https://www.youtube.com/watch?v=5fpjgXAV2BU&list=PLHqz-wcqDQIEP6p1_0wOb9l9aQ0qFijrP&ab_channel=colleenlewis" target="_blank"><button type="button" name="button" class="btn btn-purple">📺 Video: Null</button></a>

The code ``Turtle t1 = null;`` creates a variable ``t1`` that refers to a ``Turtle`` object, but the ``null`` means that it doesn't refer to an object yet. You could later create the object and set the object variable to refer to that new object (``t1 = new Turtle(world1)``).  Or more commonly, you can declare an object variable and initialize it in the same line of code (``Turtle t2 = new Turtle(world1);``).

```java
World world1 = new World();
Turtle t1 = null;
t1 = new Turtle(world1);
// declare and initialize t2
Turtle t2 = new Turtle(world1);
```

### Constructor Signatures

When you use a class that someone has already written for you in a **library** that you can **import**, like the ``Turtle`` class, you can look up how to use the constructors and methods in the <a href="https://www2.cs.uic.edu/~i101/doc/Turtle.html" target="_blank"><button type="button" name="button" class="btn btn-purple">📖 Turtle Class Documentation</button></a>. 

> The documentation will list the **signatures** (or headers) of the constructors or methods which will tell you their name and parameter list. The **parameter list**, in the **header** of a constructor, lists the **formal parameters**, declaring the variables that will be passed in as values and their data types.

For example, here are the **overloaded** constructors for the ``Turtle`` class, which take different parameters:

![image](figures/TurtleClassDefn.png)

### Formal vs. Actual Parameters

When a constructor like ``Date(2005,9,1)`` is called, the 👔 **formal parameters**, (year, month, day), are set to copies of the **actual parameters** (or **arguments**), which are (2005,9,1).  

{:.highlight}
This is **call by value**, which means that _copies_ of the actual parameter values are passed to the constructor. These values are then used to initialize the object's attributes.

![image](figures/parameterMappingDate.png)

The type of the values being passed in as arguments have to match the type of the formal parameter variables. We cannot give a constructor a ``String`` object when it is expecting an ``int``. The order of the arguments also matters. If you mix up the month and the day in the ``Date`` constructor, you will get a completely different date, for example January 9th (1/9) instead of Sept. 1st (9/1).

#### 💻 In-Class Activity
{:.no_toc}

<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit2-Using-Objects/topic-2-2-constructors.html?mode=browsing"><button type="button" name="button" class="btn">CSAwesome Topic 2.2</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: Custom Turtles** activity in pairs.

</div>

---

## ⭐️ Summary

- **Constructors** initialize the attributes in newly created objects.  They have the same name as the class.

- A **constructor signature** is the constructor name followed by the parameter list which is a list of the types of the parameters and the variable names used to refer to them in the constructor.

- **Overloading** is when there is more than one constructor.  They must differ in the number, type, or order of parameters.

- **New** is a keyword that is used to create a new object of a class.  The syntax is ``new ClassName()``.  It creates a new object of the specified class and calls a constructor.

- A **no-argument constructor** is a constructor that doesn't take any passed in values (arguments).

- **Parameters** allow values to be passed to the constructor to initialize the newly created object's attributes.

- The **parameter list**, in the header of a constructor, is a list of the type of the value being passed and a variable name. These variables are called the **formal parameters**.

- **Actual parameters** are the values being passed to a constructor.  The formal parameters are set to a copy of the value of the actual parameters.

- **Formal parameters** are the specification of the parameters in the constructor header.  In Java this is a list of the type and name for each parameter (``World(int width, int height``).

- **Call by value** means that when you pass a value to a constructor or method it passes a copy of the value.

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
