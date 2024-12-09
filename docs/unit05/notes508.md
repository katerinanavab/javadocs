---
layout: notes
title: "📓5.8: Scope" 
parent: "5️⃣ Writing Classes"
nav_order: 8
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 5.8](https://runestone.academy/ns/books/published/csawesome/Unit5-Writing-Classes/topic-5-8-scope-access.html?mode=browsing) 

---

## Scope & Access of Variables

🔎 The **scope** of a variable is defined as where a variable is _accessible_ or can be used. The scope is determined by where you **declare** the variable when you write your programs. When you **declare** a variable (like `int age;` or `String name;`), look for the _closest enclosing curly braces_ (``{ }``) -- this is its **scope**.

<div class="imp" markdown="block">
  
Java has 3 levels of _SCOPE_ that correspond to different types of variables:

- **Class Level Scope** for **instance variables** declared inside a class.

- **Method Level Scope** for **local variables** (including **parameter variables**) inside a method.

- **Block Level Scope** for **loop variables** and other local variables defined inside of blocks of code with `{ }`.

</div>

The image below shows these 3 levels of scope.

![image](Figures/scopeDiagram.png)

**Local variables** are variables that are declared inside a method, usually at the top of the method. These variables can only be used within the method and do not exist outside of the method. Parameter variables are also considered local variables that only exist for that method. It's good practice to declare any variables that are used by just one method as local variables in that method.

Instance variables at class scope are shared by all the methods in the class and can be marked as public or private with respect to their access outside of the class. They have Class scope regardless of whether they are public or private.

Another way to look at scope is that a variable's scope is where it lives and exists. You cannot use the variable in code outside of its scope. The variable does not exist outside of its scope.

Try the following code to see that you cannot access the variables outside of their scope levels in the toString() method. Explain to someone sitting next to you why you can't access these. Try to fix the errors by either using variables that are in scope or moving the variable declarations so that the variables have larger scope.

```java
public class Person {
      private String name;
      private String email;

      public Person(String initName, String initEmail) {
          name = initName;
          email = initEmail;
      }

      public String toString() {
          for (int i = 0; i < 5; i++) {
              int id = i;
          }
          // Can you access the blockScope variables i or id?
          System.out.println("i at the end of the loop is " + i);
          System.out.println("The last id is " + id);

          // Can toString() access parameter variables in Person()?
          return initName + ": " + initEmail;
      }

      // main method for testing
      public static void main(String[] args) {
          // call the constructor to create a new person
          Person p1 = new Person("Sana", "sana@gmail.com");
          System.out.println(p1);
      }
}
```

#### 💻 In-Class Activity: Debugging
{:.no_toc}

<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit5-Writing-Classes/topic-5-8-scope-access.html?mode=browsing"><button type="button" name="button" class="btn">CSAwesome Topic 5.8</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: Debugging** activity in pairs.

</div>

---

## ⭐️ Summary

- **Scope** is defined as where a variable is _accessible_ or can be used.

- **Formal parameters** declared in the _header/signature_ of a method or constructor may only be used within the constructor or method and cannot be declared to be `public` or `private`. Same goes for any **local variables** declared inside the _body_ of a method or constructor. 

- When there is a local variable with the same name as an instance variable, the variable name will refer to the local variable instead of the instance variable. Watch out!
  

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
