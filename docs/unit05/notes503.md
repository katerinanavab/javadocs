---
layout: notes
title: "📓5.3: Comments" 
parent: "5️⃣ Writing Classes"
nav_order: 3
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 5.3](https://runestone.academy/ns/books/published/csawesome/Unit5-Writing-Classes/topic-5-3-comments-conditions.html?mode=browsing) 

---

## Comments & Conditions

### Writing Useful Comments

📝 Adding **comments** to your code helps to make it more _readable_ and _maintainable_. In the commercial world, software development is usually a team effort where many programmers will use your code and maintain it for years. Commenting is essential in this kind of environment and a good habit to develop. Comments will also help you to remember what you were doing when you look back to your code a month or a year from now.

<div class="imp" markdown="block">
  
There are 3 types of **comments** in Java:

1. ``//`` Single line comment
2. ``/*`` Multiline comment ``*/``
3. ``/**`` Documentation comment ``*/``

</div>

The special characters ``//`` are used to mark the rest of the line as a comment in many programming languages.  If the comment is going to be multiple lines, we use ``/*`` to start the comment and ``*/`` to end the comment.

📚 There is also a special version of the multi-line comment, ``/**``  ``*/``, called the **documentation** comment. Java has a cool tool called [javadoc](https://www.tutorialspoint.com/java/java_documentation.htm) that comes with the [Java JDK](https://www.oracle.com/technetwork/java/javase/downloads/index.html) that will pull out all of these comments to make documentation of a class as a web page. 
> This tool generates the official Java documentation too, for example for the [String class](http://docs.oracle.com/javase/7/docs/api/java/lang/String.html).

{:.highlight}
Although you do not technically have to use this in the AP exam, it's a VERY good idea to use the documentation comment in front of **classes**, **methods**, and **instance variables** in case you want to use this tool.

The compiler will always _skip over comments_, so they don't affect how your program runs. They are for you, your teacher, and other programmers working with you. Here are some examples of good commenting:

```java
    /**
    * MyClass.java
    * @author My Name
    * @since Date
    * This class keeps track of the max score.
    */
    public class MyClass()
    {
       private int max = 10; // this keeps track of the max score
       /* The print() method prints out the max */
       public print() {  System.out.println(max); 
    }
```

Notice that there are some special tags that you can use in Java documentation. These are not required but many programmers use them. Here are some common tags:

- `@author`  Author of the program
- `@since`   Date released
- `@version` Version of program
- `@param`   Parameter of a method
- `@return`  Return value for a method

### Preconditions and Postconditions

As you write methods in a class, it is a good idea to keep in mind the **preconditions** and the **postconditions** for the method and write them in the comments:

* A **precondition** is a condition that must be `true` for your method code to work, for example the assumption that the parameters have values and are not null. The methods could check for these preconditions, but they do not have to. The precondition is _what the method expects_ in order to do its job properly.
* A **postcondition** is a condition that is `true` _after_ running the method. It is what the method promises to do. Postconditions describe the _outcome of running the method_, for example what is being returned or the changes to the instance variables. These assumptions are very useful to other programmers who want to use your class and get the correct results.

Here is an example of **preconditions**, **postconditions**, and `@param` in the Turtle code that we have used in the past for our drawing turtles:

```java

       /**
         * Constructor that takes the x and y position for the
         * turtle
         * Preconditions: parameters x and y are coordinates from 0 to
         *    the width and height of the world.
         * Postconditions: the turtle is placed in (x,y) coordinates
         * @param x the x position to place the turtle
         * @param y the y position to place the turtle
         */
        public Turtle(int x, int y)
        {
          xPos = x;
          yPos = y;
        }
```

### Software Validity and Use-Case Diagrams

Preconditions and postconditions _are_ covered on the AP CSA exam. **Software validity**, **testing**, and **use-case diagrams** which are discussed in this subsection _are not_ covered on the AP CSA exam, but they are described here because they use **preconditions** and **postconditions** and are used by professional programmers.

Determining the preconditions and postconditions help us to test our code and determine the **validity** of our software.  Software validity tests whether the software _does what it is supposed to do_ before it is released. This is sometimes very important. 
> For example, if the code is part of a satellite going to outerspace or is going to be used in an emergency condition, we want to test it thoroughly and make sure it works and is valid before it is put into use. Remember _Humble Pi?_

Preconditions and postconditions can also help us to design better software systems. Software designers often first draw a high-level **Use-Case Diagram** of a system that shows the different ways that a user might interact with a system before they build it. Here is a simple Use-Case Diagram of a restaurant system. It shows 2 actors in the system: the customer and the staff at the restaurant, and 3 use-cases in circles. A **Use-case** is a particular user interaction or situation in the system or software, and they often become methods in the program.

![image](Figures/use-case-restaurant.png)

{:.highlight} 
After drawing a Use-Case Diagram, designers write down the **preconditions** and the **postconditions** for each Use-Case. Often the successful post-condition for one use-case becomes the preconditions for the next use-case. 

For example, for the "Order Food" and "Eat Food" Use Cases:

- _Preconditions for "Order Food":_ Customer enters restaurant. Staff is ready to take the order.
- _Postconditions for "Order Food":_ Customer orders the food. Staff takes the order.
- _Preconditions for "Eat Food":_ Customer has already ordered food. Staff has delivered food.
- _Postcondition for "Eat Food":_ Customer eats the food.

<div class="task" markdown="block">
  
💬 **DISCUSS:** What are the _preconditions_ and _postconditions_ of the use-case "Pay for food"? Remember that these are often related to the other use-case conditions "order food" and "eat food".

</div>

### Agile Software Development

There are many different models for software development. The **Waterfall model**, developed in the 1970s, is a step by step model where _each phase is finished_ before the next phase begins. This model has recently been criticized because it is not very adaptable. The more recent **Agile** development model involves _iterative_, _incremental_ development where teams works in short 2-3 week **sprints** to completely develop, test, and release a component of the project to the customer for feedback. It is very adaptable as project requirements change because of early testing, immediate customer feedback and collaboration.

![image](Figures/waterfallVsAgile.png)

#### Agile Development Game
{:.no_toc}

<div class="task" markdown="block">

🎲 As a class, try the game below to practice the iterative and incremental agile development process:

<a href="https://www.agilesparks.com/blog/wake-up-in-the-morning-game/" target="_blank"><button class="btn">Wake Up In the Morning Game</button></a>

</div>

#### 💻 In-Class Activity: Comments and Conditions
{:.no_toc}

<div class="task" markdown="block">

Working in pairs or groups, come up with **4 steps** that a user must do to _purchase a product online_, for example ordering a book on Java in an online store, and list the **preconditions** and **postconditions** for each step. You could pretend to buy something online (don't actually purchase it) to come up with the steps. 
> Use an online drawing tool like [Creately.com](https://creately.com) (select **Use-Case Diagrams**) to draw a diagram for the Online Store System. Don't forget to list the preconditions and postconditions for each step. 

</div>

---

## ⭐️ Summary

- Comments are ignored by the compiler and are not executed when the program is run.

- Three types of comments in Java include ``/* */``, which generates a block of comments, ``//``, which generates a comment on one line, and ``/** */``, which are Javadoc comments and are used to create API documentation.

- A precondition is a condition that must be true just prior to the execution of a section of program code in order for the method to behave as expected. There is no expectation that the method will check to ensure preconditions are satisfied.

- A postcondition is a condition that must always be true after the execution of a section of program code. Postconditions describe the outcome of the execution in terms of what is being returned or the state of an object.

- Programmers write method code to satisfy the postconditions when preconditions are met.


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
