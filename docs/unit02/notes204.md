---
layout: notes
title: "📓2.4: Methods with Parameters" 
parent: "2️⃣ Using Objects"
nav_order: 4
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 2.4](https://runestone.academy/ns/books/published/csawesome/Unit2-Using-Objects/topic-2-4-methods-with-params.html?mode=browsing) 

<div class="setup" markdown="block">

📝 Take notes in a **Codespace** during class, coding along with the instructor.

1. Go to GitHub and click on your picture in the _TOP RIGHT_ corner
2. Select `Your repositories`
3. Open `CS2-Unit-2-Notes`
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` (unless you already have one listed there), wait for the environment to load, _then you're ready to code_!

</div>


## Calling Methods With Parameters

In the last lessons, we used simple **methods** like ``forward`` and ``turnRight`` to make the turtle draw lines. You may have noticed that ``forward()`` and ``backward()`` always move the same number of pixels (100 pixels), and ``turnRight()`` and ``turnLeft()`` always turn at right angles (90 degrees). This is a little limiting. What if we wanted to draw a triangle or the letter A? These require smaller angles to draw diagonal lines and different length lines. Luckily, there are more complex methods in the ``Turtle`` class that let you specify the number of pixels to move forward or the number of degrees to turn. These values that you can give to methods to help them do their job are called **arguments** or **parameters**.

The parentheses ``()`` after method names when we call a method are there in case you need to give the method **actual parameters** or **arguments** (some data) to do its job. For example, we can give the argument 100 in ``forward(100)`` to make the turtle go forward 100 pixels or the argument 30 in ``turn(30)`` to make the turtle turn 30 degrees instead of 90 degrees.


{:.important}
`object.method(arguments);` is used to call an object's method _and_ provide some **arguments** (actual parameters) to do its job.

### Parameters vs. Arguments

Although some people use the words _parameters_ and _arguments_ interchangeably, there is a subtle difference:
* When you define your own method, the variables you define for it are called **formal parameters**.
* When you call the method to do its job, you give or pass in **arguments** or **actual parameters** to it that are then saved in the parameter variables. 

> So, in the definition of the ``forward`` method, it has a parameter variable called ``pixels``, and in the call to ``forward(100)``, the argument is the value 100 which will get saved in the parameter variable pixels. You will learn to write your own methods in Unit 5. In this unit, you will learn to call methods that are already written for you.

```java
// Method call
yertle.forward(100); // ARGUMENT is 100

// Method definition written for you in the Turtle class
public void forward(int pixels) // PARAMETER is pixels
```

### Tracing Methods

You will not write your own methods until Unit 5, but you should be able to **trace** and **interpret** method calls.

Check out another version of the Old MacDonald Song with a more powerful **abstraction**. The method `verse` now takes **2 parameters** for the `animal` and the `noise` it makes, so that it can be used for any animal. Use the <a href="http://www.pythontutor.com/java.html#code=public%20class%20Song%20%0A%7B%0A%20%20%0A%20%20%20%20public%20void%20verse%28String%20animal,%20String%20noise%29%20%0A%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20System.out.println%28%22Old%20MacDonald%20had%20a%20farm%22%29%3B%0A%20%20%20%20%20%20%20%20chorus%28%29%3B%0A%20%20%20%20%20%20%20%20System.out.println%28%22And%20on%20that%20farm%20he%20had%20a%20%22%20%2B%20animal%29%3B%0A%20%20%20%20%20%20%20%20chorus%28%29%3B%0A%20%20%20%20%20%20%20%20System.out.println%28%22With%20a%20%22%20%2B%20noise%20%2B%20%22%20%22%20%2B%20noise%20%2B%20%22%20here,%22%29%3B%0A%20%20%20%20%20%20%20%20System.out.println%28%22And%20a%20%22%20%2B%20noise%20%2B%20%22%20%22%20%2B%20noise%20%2B%20%22%20there,%22%29%3B%0A%20%20%20%20%20%20%20%20System.out.println%28%22Old%20MacDonald%20had%20a%20farm%22%29%3B%0A%20%20%20%20%20%20%20%20chorus%28%29%3B%0A%20%20%20%20%7D%0A%20%20%20%20public%20void%20chorus%28%29%0A%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20System.out.println%28%22E-I-E-I-O%22%29%3B%0A%20%20%20%20%7D%0A%20%20%20%20%0A%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%20%0A%20%20%20%20%7B%0A%20%20%20%20%20%20%20Song%20s%20%3D%20new%20Song%28%29%3B%0A%20%20%20%20%20%20%20s.verse%28%22cow%22,%20%22moo%22%29%3B%0A%20%20%20%20%20%20%20s.verse%28%22duck%22,%22quack%22%29%3B%0A%20%20%20%20%7D%0A%7D&cumulative=false&curInstr=1&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false" target="_blank" style="text-decoration:underline">Java Visualizer</a> to step through the code.

#### 💻 In-Class Activity
{:.no_toc}

<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit2-Using-Objects/topic-2-4-methods-with-params.html?mode=browsing"><button type="button" name="button" class="btn">CSAwesome Topic 2.4</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: Turtle House** activity in pairs.

</div>

---

## ⭐️ Summary

- **Methods** define the behaviors or functions for objects.

- To use an object's method, you must use the object name and the dot (.) operator followed by the method name, for example **object.method();**

- Some methods take parameters/arguments that are placed inside the parentheses **object.method(arguments)**.

- Values provided in the parameter list need to correspond to the order and type in the method signature.

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
