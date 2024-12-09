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

Up until this unit, you wrote all your code in the main method, but now we are using lots of methods. Why have multiple methods instead of just one? **Procedural Abstraction** allows us to name a block of code as a method and call it whenever we need it, abstracting away the details of how it works. 
> This serves to organize our code by function and reduce its complexity and reduce the repetition of code. In addition, it helps with debugging and maintenance since changes to that block of code only need to happen in one place.

Here are some of the main reasons to use multiple methods in your programs:

- **Organization and Reducing Complexity:** organize your program into small sections of code by function to reduce its complexity. Divide a problem into subproblems to solve it a piece at a time.
- **Reusing Code:** avoid repetition of code. Reuse code by putting it in a method and calling it whenever needed.
- **Maintainability and Debugging:** smaller methods are easier to debug and understand than searching through a large main method.

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
3. **Method Definition**: write the method's **header** and **body** code like below:
```java
// Step 3: Define the method in the class
// Method HEADER/SIGNATURE
public void methodName() {
    // Method BODY for the repeatable code
}
```
</div>


#### 💻 In-Class Activity: 
{:.no_toc}


<div class="task" markdown="block">
1. Go to <a href=""><button type="button" name="button" class="btn">CSAwesome Topic 5.0</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: ** activity in pairs.

</div>

---

## ⭐️ Summary


  

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
