---
layout: notes
title: "📓2.3: Methods without Parameters" 
parent: "2️⃣ Using Objects"
nav_order: 3
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 2.3](https://runestone.academy/ns/books/published/csawesome/Unit2-Using-Objects/topic-2-3-methods-no-params.html?mode=browsing) 

<div class="setup" markdown="block">

📝 Take notes in a **Codespace** during class, coding along with the instructor.

1. Go to GitHub and click on your picture in the _TOP RIGHT_ corner
2. Select `Your repositories`
3. Open `CS2-Unit-2-Notes`
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` (unless you already have one listed there), wait for the environment to load, _then you're ready to code_!

</div>


## Calling Methods Without Parameters

{:.highlight}
**Methods** are a set of instructions that define **behaviors** for all objects of a class. 

> _Example:_ in the ``Turtle`` class, methods like ``forward()`` and ``turnRight()`` give ``Turtle`` objects the ability to move forward and turn 90 degrees right.

To use an object's method, you must use the object name and the **dot `.` operator** followed by the method name, for example, ``yertle.forward();`` calls ``yertle``'s ``forward`` method to move a turtle object forward 100 pixels. These are called **object methods** or **non-static methods**. An object method *must* be called on an object of the class that the method is defined in.  Object methods work with the **attributes** of the object, such as the direction the turtle is heading or its position.

Every method call is followed by **parentheses**. The parentheses ``()`` after method names are there in case you need to give the method parameters (data) to do its job, which we will see in the next lesson. You must always include the parentheses after the method name.


{:.important}
📣 `object.method();` is used to **call** an object's method!

### Procedural Abstraction

**Procedural abstraction** allows a programmer to use a method and not worry about the details of how it exactly works. For example, we know that if we hit the brakes, the car will stop, and we can still use the brakes even if we don't really know how they work.

You will learn to write your own methods in Unit 5. In this unit, you should be able to **use** methods already written for you and figure out what they do. 

> Click the **DevDocs** link in the top navigation bar to find the official Java documentation.

{:.important}
When we use methods for a class in a library, we can look up the **method signature** (or **method header**), which is the method name followed by a **parameter list**, in its official documentation. 

For example, here is a ``Student`` class with a method signature ``public void print()`` which has an empty parameter list with no parameters. Methods are defined after the instance variables (attributes) and constructors in a class.

![image](figures/StudentClass.png)

#### VISUALIZATION
{:.no_toc}

This Java <a href="http://www.pythontutor.com/java.html#code=public%20class%20Song%20%7B%0A%20%20%0A%20%20%20%20public%20void%20print%28%29%20%7B%0A%20%20%20%20%20%20%20%20System.out.println%28%22Old%20MacDonald%20had%20a%20farm%22%29%3B%0A%20%20%20%20%20%20%20%20chorus%28%29%3B%0A%20%20%20%20%20%20%20%20System.out.print%28%22And%20on%20that%20farm%20he%20had%20a%20%22%29%3B%0A%20%20%20%20%20%20%20%20animal%28%29%3B%0A%20%20%20%20%20%20%20%20chorus%28%29%3B%0A%20%20%20%20%7D%0A%20%20%20%20public%20void%20chorus%28%29%0A%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20System.out.println%28%22E-I-E-I-O%22%29%3B%0A%20%20%20%20%7D%0A%20%20%20%20%0A%20%20%20%20public%20void%20animal%28%29%20%7B%0A%20%20%20%20%20%20%20System.out.println%28%22duck%22%29%3B%0A%20%20%20%20%7D%0A%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%20%7B%0A%20%20%20%20%20%20%20Song%20s%20%3D%20new%20Song%28%29%3B%0A%20%20%20%20%20%20%20s.print%28%29%3B%0A%20%20%20%20%7D%0A%7D&cumulative=false&curInstr=1&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false" target="_blank" style="text-decoration:underline">visualization</a> shows how a song can be divided up into methods. Click on the **next** button below the code to step through the code. 

> Execution in Java always begins in the ``main`` method in the current class. Then, the flow of control skips from method to method as they are called.

The Song's print method calls the `chorus()` and `animal()` methods to help it print out the whole song.

When you call the `chorus()` method, it skips to the chorus code, executes and prints out the chorus, and then returns back to the method that called it.

{:.important}
**SCOPE:** Methods _inside the same class_ can call each other using just ``methodName()``, but to call non-static methods in _another class_ or from a _main method_, you must first **create an object instance** of that class, and then call its methods using the **dot operator** like this: ``object.methodName()``.

![image](figures/calling-methods.png)

> Remember that if you just declare an object reference without setting it to refer to a new object, the value will be ``null`` meaning that it doesn't reference an object. If you call a method on a variable whose value is ``null``, you will get a `NullPointerException` error, where a **pointer** is another name for a reference.

#### 💻 In-Class Activity
{:.no_toc}

<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit2-Using-Objects/topic-2-3-methods-no-params.html?mode=browsing"><button type="button" name="button" class="btn">CSAwesome Topic 2.3</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: Draw a Letter** activity on your own.

</div>

---

## ⭐️ Summary

- **Methods** are a set of instructions that define the behaviors for all objects of the class.

- Use **dot notation** to execute an object's method.  This is the object's name followed by the dot (.) operator followed by the method name and parentheses: **object.method();**

- A **method signature** is the method name followed by the parameter list which gives the type and name for each parameter. Note that methods do not have to take any parameters, but you still need the parentheses after the method name.

- **Procedural abstraction** allows a programmer to use a method by knowing in general what it does without knowing what lines of code execute. This is how we can drive a car without knowing how the brakes work.

- A **method** or **constructor** call interrupts the sequential execution of statements, causing the program to first execute the statements in the method or constructor before continuing. Once the last statement in the method or constructor has executed or a ``return`` statement is executed, the flow of control is returned to the point immediately following the method or constructor call.

- A **NullPointerException** will happen if you try to call an object method on an object variable whose value is ``null``.  This usually means that you forgot to create the object using the ``new`` operator followed by the class name and parentheses.

- An **object method** or **non-static method** is one that must be called on an object of a class.  It usually works with the object's attributes.

- A **static method** or **class method** method is one that doesn't need to be called on an object of a class.
  
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
