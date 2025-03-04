---
layout: notes
title: "📓9.4: super Keyword" 
parent: "9️⃣ Inheritance"
nav_order: 4
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 9.4](https://runestone.academy/ns/books/published/csawesome/Unit9-Inheritance/topic-9-4-super.html) 

---

## The `super` Keyword

Sometimes you want the subclass to do more than what a superclass' method is doing.  You want to _still execute_ the superclass method, but you also want to **override** the method to do _something additional_. 
> But, since you have overridden the parent method, how can you still call it?  You can use ``super.method()`` to force the parent's method to be called.

We've used `super()` before to call the superclass' **constructor**. But there are two uses of the keyword `super`:

1. `super();` or `super(arguments);` calls just the super **constructor** if put in as the first line of a subclass constructor.
2. `super.method();`calls a superclass' **method** (_not constructors_).

The keyword `super` is very useful in allowing us to first execute the superclass method, and then _add on to what it does_ in the subclass.

In the example below, the ``Student`` class overrides the ``getFood`` method of the ``Person`` class, and it uses ``super.getFood()`` to call the ``Person`` ``getFood`` method before adding on to it. Here, a ``Person`` is associated with the food "Hamburger" and a ``Student`` is associated with "Hamburger" and "Taco".

```java
public class Person {
   private String name;

   public Person(String theName) {
           name = theName;
   }

   public String getFood() {
      return "Hamburger";
   }

   public static void main(String[] args) {
      Person p = new Student("Javier");
      System.out.println(p.getFood());
   }
}
```
```java
public class Student extends Person {
   private int id;
   private static int nextId = 0;

   public Student(String theName) {
      super(theName);
      id = nextId;
      nextId++;
   }

   public String getFood() {
      String output = super.getFood();
      return output + " and Pizza";
   }

   public int getId() {
      return this.id;
   }

   public void setId(int theId) {
      this.id = theId;
   }
}
```
> 💻 **TRY IT OUT:** Add another subclass called `Vegan` that inherits from the `Student` class. Add a **constructor** that takes a `name` as an argument and passes it to the `super()` constructor. **Override** the `getFood()` method in `Vegan` to call the superclass `getFood()`, but add a "No " in front of it and then say "but " and add a vegan food. Change Javier to a Vegan object in `main()` and try it out!


How does this work?  Remember that an object always _keeps a reference to the class that created it_ and always looks for a method during execution starting in the class that created it.  
* If it finds the method in the **child** class that created it, it will execute that method.
* If it doesn't find it in the class that created it, it will look at the **parent** of that class.
   * It will keep looking up the **ancestor chain** until it finds the method, all the way up to the `Object` class. The method has to be there, or else the code would not compiled!

⛓️ When the student ``getFood()`` method is executed it will start executing the ``getFood`` method in ``Student``.  When it gets to ``super.getFood()`` it will execute the ``getFood`` method in ``Person``.  This method will return the string ``"Hamburger"``.  Then execution will continue in the ``getFood`` method of ``Student`` and  return the string ``"Hamburger and Taco"``.

### toString Override

The ``toString`` method is commonly overridden. A subclass can override ``toString``, but in its new ``toString`` method, it can also call
``super.toString()`` to get a starting String to which it can _add on its own_ instance variables:

```java
// overridden toString() in subclass
public String toString() {
   return (super.toString() + "\n" + subclassInstanceVariables);
}
```


#### 💻 In-Class Activity: Customer Info
{:.no_toc}


<div class="task" markdown="block">
    
1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit9-Inheritance/topic-9-4-super.html"><button type="button" name="button" class="btn">CSAwesome Topic 9.4</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: Customer Info** activity in pairs.

</div>

---

## ⭐️ Summary

- The keyword `super` can be used to call a superclass’s **constructors** and **methods**.
    - The superclass method can be called in a subclass by using the keyword `super` with the **method name** and passing appropriate **parameters**.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
