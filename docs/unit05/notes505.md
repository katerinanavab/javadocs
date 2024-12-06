---
layout: notes
title: "📓5.5: Mutators/Setters" 
parent: "5️⃣ Writing Classes"
nav_order: 5
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 5.5](https://runestone.academy/ns/books/published/csawesome/Unit5-Writing-Classes/topic-5-5-mutator-methods.html?mode=browsing) 

---

## Mutator Methods (_Setters_)

As we saw in the last section, since we typically make instance variables
``private``, we have to define getters if we want to allow code outside the
class to access the value of particular instance variables.

{:.highlight} 
By the same token, if we want to allow code outside the class to `change` the value of an instance variable we have to provide what is formally called a
**mutator method** but which everyone actually calls a **setter**. A setter is a `void` method with a name that starts with ``set`` and that takes a single
argument of the same type as the instance variable to be set. 
> The **effect** of a setter, as you would probably expect, is to assign the provided value to the instance variable.

Just as you shouldn't reflexively write a getter for every instance variable,
you should think even harder about whether you want to write a setter. Not all
instance variables are meant to be **manipulated directly** by code outside the
class.
> For example, consider the ``Turtle`` class. It provides getters ``getXPos`` and
``getYPos`` but it _does not provide corresponding setters_. There are, however,
methods that change a ``Turtle``\ ’s position like ``forward`` and ``moveTo``.
But they do more than just changing the values of instance variables; they also
take care of drawing lines on the screen if the pen is down. 

### How to Define a Setter

<div class="imp" markdown="block">

A setter is a `void` method with a name that starts with ``set`` and that takes a **single
argument** of the same type as the instance variable to be set. The effect of a
setter is to assign the new provided value to the object's instance variable.

```java
     public class ExampleTemplate
     {
         // Instance variable declaration
         private typeOfVar varName;

         // Setter method template
         public void setVarName(typeOfVar newValue)
         {
             varName = newValue;
         }
     }
```
</div>

Here's an example of the ``Student`` class with a setter for the ``name`` variable:

```java
  public class Student
  {
      // Instance variable name
      private String name;

      /**
       * setName sets name to newName
       *
       * @param newName
       */
      public void setName(String newName)
      {
          name = newName;
      }

      public static void main(String[] args)
      {
          // To call a set method, use objectName.setVar(newValue)
          Student s = new Student();
          s.setName("Ayanna");
      }
  }
```

Notice the difference between setters and getters in the following figure.
* Getters `return` an instance variable's **value** and have the same return type as this variable and **no parameters**. 
* Setters have a `void` return type and **take a new value as a parameter** to change the value of the instance variable.

![image](Figures/get-set-comparison.png)

#### 💻 In-Class Activity: Class Pet
{:.no_toc}


<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit5-Writing-Classes/topic-5-5-mutator-methods.html?mode=browsing"><button type="button" name="button" class="btn">CSAwesome Topic 5.5</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: Class Pet** activity in pairs.

</div>

---

## ⭐️ Summary

- A void method does not return a value. Its header contains the keyword ``void`` before the method name.

- A **mutator method** or **setter** is a void method that _changes the values_ of an instance or static
  variable.
  

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
