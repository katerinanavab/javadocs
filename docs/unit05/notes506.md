---
layout: notes
title: "📓5.6: Writing Methods" 
parent: "5️⃣ Writing Classes"
nav_order: 6
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 5.6](https://runestone.academy/ns/books/published/csawesome/Unit5-Writing-Classes/topic-5-6-writing-methods.html?mode=browsing) 

---

## Writing Methods

Up until this unit, you wrote all your code in the main method, but now we are using lots of methods. Why have multiple methods instead of just one? 

{:.highlight}
**Procedural Abstraction** allows us to name a block of code as a **method** and call it whenever we need it, _abstracting_ away the details of how it works. 
> This serves to _organize_ our code by function and _reduce repetition_ of code. In addition, it helps with debugging and maintenance since changes to that block of code only need to happen in one place!

Here are some of the main reasons to use multiple methods in your programs:

- **Organization and Reducing Complexity:** organize your program into small sections of code by function to reduce its complexity. Divide a problem into subproblems to solve it a piece at a time.
- **Reusing Code:** avoid repetition of code. Reuse code by putting it in a method and calling it whenever needed.
- **Maintainability and Debugging:** smaller methods are easier to debug and understand than searching through a large main method.

### How to Write a Method

<div class="imp" markdown="block">

There are three steps to creating and calling a custom **method**:

1. **Object of the Class**: Declare an object of your class in the main method or from outside the class.
```java
// Step 1: declare an object from outside the class
Classname objectName = new Classname();
```
2. **Method Call**: whenever you want to use the method, call objectName.methodName();
```java
// Step 2: call the object's method from outside the class
objectName.methodName(); 
```
3. **Method Definition**: write the method's **header/signature** and **body** code like below:
```java
// Step 3: Define the method in the class
// Method HEADER/SIGNATURE
public void methodName() {
    // Method BODY for the repeatable code
}
```
</div>

### Formal Parameters

<div class="imp" markdown="block">

🤵‍♀️🤵🤵‍♂️ When you **define** your own method, the variables you specify for it in the method header are called **formal parameters**. 

📣 When you **call** the method to do its job, you give or pass in **arguments** or **actual parameters** to it that are then saved in these local parameter variables.

</div>

When a method is called, the right method definition is found by checking the **method signature** or **header** at the top of the method definition to **match** the following:

1. The method name
2. The number of arguments
3. The data types for the arguments
4. The `return` type

Here's what that looks like with the 2 method calls above. Notice how the parameter variables get new values with every method call.

![image](Figures/args2params.png)

{:.warning}
Java uses **Call by Value** when it passes arguments to methods. This means that a _copy_ of the value in the argument is saved in the parameter variable. If the parameter variable changes its value inside the method, the original value outside the method is not changed.

If you pass in an argument that holds a reference to an object, like a String or Person or Turtle object, a _copy_ of this reference is passed in and saved in the parameter variable. The formal parameter and the actual parameter (argument) are then **aliases**, both refering to the same object. Java was designed this way to avoid copying large objects from method to method. Remember when we discussed reference aliases with turtle objects who are set equal to one another.

![image](Figures/turtleEquality.png)

{:.highlight}
Methods can also **return** values of any type back to the calling method, like we saw when writing **getter/accessor** methods. The calling method should then _do something_ with this `return` value, like printing it out or assigning it to a variable.

#### 💻 In-Class Activity: Song with Parameters
{:.no_toc}

<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit5-Writing-Classes/topic-5-6-writing-methods.html?mode=browsing"><button type="button" name="button" class="btn">CSAwesome Topic 5.6</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: Song with Parameters** activity in pairs.

</div>

---

## ⭐️ Summary

- **Procedural Abstraction** (creating methods) reduces the complexity and repetition of code. We can name a block of code as a method and call it whenever we need it, abstracting away the details of how it works.

- A programmer breaks down a large problem into smaller subproblems by creating methods to solve each individual subproblem.

- To write methods, write a **method definition** with a **method signature** like "public void chorus()" and a **method body** in {} and method calls using an object.the method name and arguments whenever you need it to do its job.

- To call an object's method, you must use the object name and the dot (.) operator followed by the method name, for example **object.method();**


- When you call a method, you can give or pass in **arguments** or **actual parameters** to it inside the parentheses **object.method(arguments)**. The arguments are saved in local **formal parameter** variables that are declared in the method header, for example: public void method(type param1, type param2) { ... }.

- Values provided in the arguments in a method call need to correspond to the order and type of the parameters in the method signature.

- When an actual parameter is a primitive value, the formal parameter is initialized with a copy of that value. Changes to the formal parameter have no effect on the corresponding actual parameter.

- When an actual parameter is a reference to an object, the formal parameter is initialized with a copy of that reference, not a copy of the object. The formal parameter and the actual parameter are then aliases, both refering to the same object.

-  When an actual parameter is a reference to an object, the method or constructor could use this reference to alter the state of the original object. However, it is good programming practice to not modify mutable objects that are passed as parameters unless required in the specification.
  

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
