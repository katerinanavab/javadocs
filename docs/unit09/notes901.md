---
layout: notes
title: "📓9.1: Class Inheritance" 
parent: "9️⃣ Inheritance"
nav_order: 1
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 9.1](https://runestone.academy/ns/books/published/csawesome/Unit9-Inheritance/topic-9-1-inheritance.html?mode=browsing) 

#### Using a GitHub Template for class notes 
{:.no_toc}

<div class="setup" markdown="block">

1. Go to the public template **repository** for our class: [BWL-CS Java Template](https://github.com/BWL-CS/java-template)
2. Click the <button type="button" name="button" class="btn btn-green">Use this template</button> button above the list of files then select `Create a new repository`
3. Specify the **repository name**: `CS2-Unit-9-Notes`
4. Click <button type="button" name="button" class="btn btn-green">Create repository</button>
    > Now you have **your own personal copy** of this starter code that you can always access under the `Your repositories` section of GitHub! 
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` and wait for the environment to load, _then you're ready to code_!
7. 📝 Take notes in this Codespace during class, coding along with the instructor.

</div>

---

## Class Inheritance

One of the really useful features of Object-Oriented programming is **inheritance**.  You may have heard of someone coming into an inheritance, which often means they were left something from a relative who died.  Or, you might hear someone say that they have inherited musical ability from a parent.  In Java all classes can **inherit** attributes (instance variables) and behaviors (methods) from another class.  The class being inherited from is called the **parent class** or **superclass**.  The class that is inheriting is called the **child class** or **subclass**.

When one class inherits from another, we can say that it is the *same kind of thing* as the **parent class** (the class it inherits from).  For example, a car is a kind of vehicle.  This is sometimes called the *is-a* relationship, but more accurately it's a *is-a kind of* relationship.  A motorcycle is another kind of vehicle.  All vehicles have a make, model, and year that they were created.  All vehicles can go forward, backward, turn left and turn right.

![image](Figures/vehicle.png)

A **UML (Unified Modeling Language) class diagram** shows classes and the relationships between the classes as seen above.  An open triangle points to the **parent** class.  
> The parent class for ``Car`` and ``Motorcycle`` is ``Vehicle``. The ``Vehicle`` class has two child classes or subclasses: ``Car`` and ``Motorcycle``.

### Subclass `extends` Superclass

To make a subclass inherit from a superclass, use the Java keyword `extends` with the superclass name when creating a new subclass as shown below.

```java
public class Car extends Vehicle {}
public class Motorcycle extends Vehicle {}
```

{:.highlight}
While a human can have two parents, a Java class **can only inherit from _ONE_ parent class**. If you leave off the `extends` keyword when you declare a class, then the class will inherit from the ``Object`` class that is already defined in Java.

#### Why Use Inheritance?
{:.no_toc}

Inheritance allows you to **reuse data and behavior** from the parent class.  If you notice that several classes share the same data and/or behavior,  you can pull that out into a parent class.  This is called **generalization**. 
> For example, `Customers` and `Employees` are both people, so it makes sense use the general `Person` class as seen below.

Inheritance is also useful for **specialization** which is when you want most of the behavior of a parent class, but want to do at least one thing differently and/or add more data.  The example below can also be seen as specialization.  An employee is a person but also has a unique id.  A customer is a person, but also has a credit card.

![image](Figures/person.png)

The `Student` class can also **inherit** from the class `Person` just like `Employee` and `Customer` because a `Student` ***is a** type of* `Person`.

<div class="task" markdown="block">

* 💻 **FIX CODE:** What do you need to add to the `Student` class declaration below to make it **inherit** from type `Person`? 
    > When you fix the code below, the `instanceof` operator would return `true` that `Student s` _is an **instance** of_ both the `Student` and the `Person` class. 

```java
public class Person {
    private String name;
}
```
```java
public class Student {
    private int id;

    public static void main(String[] args) {
        Student s = new Student();
        System.out.println(s instanceof Student);
        System.out.println(s instanceof Person);
    }
}
```

* 💬 **DISCUSS:** What other private instance variables could you add to `Person` and `Student`? In which class would you put an _address_ attribute? Where would you put _GPA_?

</div>

### IS-A vs. HAS-A Relationships

Another type of relationship between classes is the **has-a** relationship or **association** relationship.  Use this when the object of one class contains a reference to one or more of another class.  For example, a course can have many course periods associated with it as shown below.  The ``1`` near the ``Course`` means that ``1`` course object is associated with the number shown near the other class.  In this case it is ``*`` which means 0 to many.  So one course is associated with 0 to many course periods.

![image](Figures/assoc.png)

In the code, the ``Course`` class **has** an array or ArrayList of ``CoursePeriod`` objects as an attribute inside it.

```java
public class Course {
    private ArrayList<CoursePeriod> periodList;
}
```

Alternatively, we could say that a CoursePeriod  has a Course attribute inside it to hold the information about the Course. It is up to the programmer how to design these two classes depending on which type of association would be more useful in the program.

```java
public class CoursePeriod {
    private Course courseInfo;
    private int period;
}
```

Here is another example. Consider the classes Student, Course, and  APcourse. An APcourse is a special type of Course. Students are in Courses. What are the relationships between these classes? The UML diagram below shows the inherits (is-a) relationship between Course and APcourse and the associate (has-a) relationship between Course and Students.

![image](Figures/APcourseUML.png)

#### is-a Substitution Test

If you aren't sure if a class should inherit from another class ask yourself if you can substitute the subclass type for the superclass type. For example, if you have a ``Book`` class and it has a subclass of ``ComicBook`` does that make sense?  Is a comic book a kind of book?  Yes, a comic book **is a kind of** book so inheritance makes sense.  If it doesn't make sense use *association* or the *has-a* relationship instead.

{:.highlight}
Only use **inheritance** (_is-a_) when the child class is truly a **type of** the parent class, otherwise use **association** (_has-a_).

#### 💻 In-Class Activity: Online Store
{:.no_toc}


<div class="task" markdown="block">
    
1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit9-Inheritance/topic-9-1-inheritance.html?mode=browsing"><button type="button" name="button" class="btn">CSAwesome Topic 9.1</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: Online Store** activity in pairs.

</div>

---

## ⭐️ Summary

- A class hierarchy can be developed by putting common attributes and behaviors of related classes into a single class called a **superclass**.

- Classes that extend a superclass, called **subclasses**, can draw upon the existing attributes and behaviors of the superclass without repeating these in the code.

- The keyword **extends** is used to establish an **inheritance** relationship between a **subclass** and a **superclass**.  A class can extend only one superclass.
    - Extending a subclass from a superclass creates an **is-a relationship** from the subclass to the superclass.


<div class="warn" markdown="block">

🛑 When class ends, don't forget to **SAVE YOUR WORK**!

1. Navigate to the `Source Control` menu on the _LEFT_ sidebar
2. Type a brief **commit message** in the box, for example: `updated Main.java`
3. Click the <button type="button" name="button" class="btn btn-green">commit changes</button> button on the _LEFT_ menu
4. Click the <button type="button" name="button" class="btn btn-green">sync changes</button> button on the _LEFT_ menu
5. _Finally you can close your Codespace!_

</div>

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
