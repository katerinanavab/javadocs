---
layout: notes
title: "📓4.1: While Loops" 
parent: "4️⃣ Iteration"
nav_order: 1
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 4.1](https://runestone.academy/ns/books/published/csawesome/Unit4-Iteration/topic-4-1-while-loops.html?mode=browsing) 

#### Using a GitHub Template for class notes
{:.no_toc}

<div class="setup" markdown="block">

1. Go to the public template **repository** for our class: [BWL-CS Java Template](https://github.com/BWL-CS/java-template)
2. Click the <button type="button" name="button" class="btn btn-green">Use this template</button> button above the list of files then select `Create a new repository`
3. Specify the **repository name**: `CS2-Unit-4-Notes`
4. Click <button type="button" name="button" class="btn btn-green">Create repository</button>
    > Now you have **your own personal copy** of this starter code that you can always access under the `Your repositories` section of GitHub! 
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` and wait for the environment to load, _then you're ready to code_!
7. 📝 Take notes in this Codespace during class, coding along with the instructor.

</div>


## While Loops

![image](Figures/loops.png)

When you play a song, you can set it to loop, which means that when it reaches
the end it starts over at the beginning. A **loop** in programming, also called
**iteration** or **repetition**, is a way to repeat one or more statements. If
you didn't have loops to allow you to repeat code, your programs would get very
long very quickly! Using a sequence of code, selection (ifs), and repetition
(loops), the **control structures** in programming, you can construct an
algorithm to solve almost any programming problem!

A ``while`` loop executes the body of the loop as long as (or while) a ``boolean``
condition is true. When the condition is false, we exit the loop and continue
with the statements that are after the body of the ``while`` loop. If the
condition is false the first time you check it, the body of the loop will not
execute.

Notice the ``while`` statement looks a lot like an ``if`` statement, but it runs
more than once. The curly braces (``{}``) are optional when there is just 1
statement following the condition, but required if there are more than 1
statement in the loop. In the AP exam, they will always use curly braces, which
is a good practice to follow.

```java

    // The statements in an if run one time if the condition is
    // is true and zero times if it is false.
    if (condition) {
        statements;
    }

    // The statements in a while loop run zero or more times,
    // determined by how many times the condition is true
    while (condition) {
        statements;
    }
```

Here's what the flow of control looks like in a Java while loop. Notice that while the condition is true, the loop body is repeated.

![image](Figures/WhileLoopFlow.png)

### Three Steps to Writing a Loop

The simplest loops are **counter-controlled loops** like below, where the **loop control variable** is a counter that controls how many times to repeat the loop. There are 3 steps to writing a loop using this loop control variable as seen below in a loop that counts from 1 to 10.

![image](Figures/loop3steps.png)

<div class="imp" markdown="block">

🔄 Remember these 3 steps to writing a loop:

1. **Initialize** the loop variable (before the ``while`` loop)
2. **Test** the loop variable (in the loop header)
3. **Change** the loop variable (in the while loop body at the end)

</div>

### Tracing Loops

A really important skill to develop is the ability to trace the values of variables and how they change during each iteration of a loop. 

You can create a tracing table that keeps track of the variable values each time through the loop as shown below.  This is very helpful on the exam. Studies have shown that students who create tables like this do much better on code tracing problems on multiple choice exams.

![image](Figures/traceTable.png)

> A trace table shows the values of all of the **variables** each time through the loop. `Iteration 0` means **before** the loop. When you are tracing through code, pretend to be the computer running the code line by line, repeating the code in the loop, and keeping track of the variable values and output.

<a href="https://www.youtube.com/watch?v=TZss5ukwN8s" target="_blank"><button type="button" name="button" class="btn">📺 VIDEO: Loop Tracing</button></a>

### Common Errors with Loops

One common error with loops is to accidentally create an ♾️ **infinite loop** ♾️. An
infinite loop is one that never stops because the _condition is always true_.

Sometimes we will write an infinite loop on purpose like this:

```java
   while (true) {
       System.out.println("This is a loop that never ends");
   }
```

But if we create an infinite loop by accident, our program may seem to get
stuck. For example look at this loop:

```java

   int i = 0;
   while (i < 10) {
       System.out.println(i);
   }
```
> That loop looks a lot like loops earlier in this chapter but it is actually an
infinite loop. Can you see why?

The problem in this loop—and a common way to accidentally create an infinite
``while`` loop—is that although it includes steps 1 and 2 (initializing the loop
variable and testing it) it forgot step 3 and never changes the loop variable.
The loop variable, ``i``, starts at ``0`` and the loop loops as long as ``i <
10`` which will always be true because there’s no code in the loop that changes
``i``. The simple fix is to add a line that increments ``i``:

```java
   int i = 0;
   while (i < 10) {
       System.out.println(i);
       i++;
   }
```

Another common error with loops is an **off-by-one error** where the loop runs
one too many or one too few times. This is usually a problem with step 2 the
test condition and using the incorrect relational operator ``<`` or ``<=``.


### Input-Controlled Loops

You can use a ``while`` loop to repeat the body of the loop a certain number of times as shown above.  However, a ``while`` loop is typically used when you don't know how many times the loop will execute. It is often used for a **input-controlled loop** where the user's input indicates when to stop. For example, in the <a href="https://firewalledreplit.com/@BerylHoffman/Magpie-ChatBot-Lab-v2#Main.java" target="_blank">Magpie chatbot lab on replit.com</a> below, the while loop stops when you type in "Bye". The stopping value is often called the **sentinel value** for the loop. Notice that if you type in "Bye" right away, the loop will never run. If the loop condition evaluates to false initially, the loop body is not executed at all. Another way to stop the loop prematurely is to put in a ``return`` statement that makes it immediately return from the method.

<html>
<iframe height="700px" width="100%" style="max-width:90%; margin-left:5%" src="https://firewalledreplit.com/@BerylHoffman/Magpie-ChatBot-Lab-v2?lite=true#Main.java" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe> 
</html>


#### 💻 In-Class Activity: Guessing Game
{:.no_toc}

<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit4-Iteration/topic-4-1-while-loops.html?mode=browsing"><button type="button" name="button" class="btn">CSAwesome Topic 4.1</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: Guessing Game** activity in pairs.

</div>

---

## ⭐️ Summary


- Iteration statements (loops) change the flow of control by repeating a set of statements zero or more times until a condition is met.

- Loops often have a **loop control variable** that is used in the boolean condition of the loop. Remember the 3 steps of writing a loop:

  - Initialize the loop variable
  - Test the loop variable
  - Change the loop variable

- In ``while`` loops, the Boolean expression is evaluated before each iteration
  of the loop body, including the first. When the expression evaluates to true,
  the loop body is executed. This continues until the expression evaluates to
  false which signals to exit the loop.

- If the Boolean expression evaluates to false initially, the loop body is not
  executed at all.

- A loop is an **infinite loop** when the Boolean expression always evaluates to
  true so that the loop never ends.

- **Off-by-one** errors occur when the iteration statement loops one time too
  many or one time too few.

- **Input-controlled loops** often use a **sentinel value** that is input by the
  user like "bye" or -1 as the condition for the loop to stop. Input-controlled
  loops are not on the AP CSA exam, but are very useful to accept data from the
  user.


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
