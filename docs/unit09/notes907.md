---
layout: notes
title: "📓9.7: Object Superclass" 
parent: "9️⃣ Inheritance"
nav_order: 7
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 9.7](https://runestone.academy/ns/books/published/csawesome/Unit9-Inheritance/topic-9-7-Object.html) 

---

## Object Superclass

The ``Object`` class is the **superclass** of ALL other classes in Java and a part
of the built-in ``java.lang`` package. 

If a parent class isn’t specified using the ``extends`` keyword, the class will inherit from the ``Object`` class. What
does a class inherit from the ``Object`` class? 

The [AP CSA Reference Sheet](https://apstudents.collegeboard.org/ap/pdf/ap-computer-science-a-java-quick-reference_0.pdf) lists the two main methods that are most frequently used:

- ``String toString()``
- ``boolean equals(Object other)``

### ``toString()`` method

One commonly overridden ``Object`` method is ``toString()``, which is often used
to print out the attributes of an object. It is a good idea to write your own
``toString()`` method in every class. In a subclass, ``toString()`` can call the
superclass ``toString()`` method using ``super.toString()`` and then add on its
own attributes.

In the following code, the ``Person`` class overrides the ``toString`` method
from ``Object`` method and the ``Student`` class then overrides it again. In
each class the new ``toString`` method adds the new attributes from that class.

```java
  public class Person
  {
      private String name;

      public Person(String name)
      {
          this.name = name;
      }

      public String toString()
      {
          return name;
      }

      public static void main(String[] args)
      {
          Person p = new Person("Sila");
          Student s = new Student("Tully", 1001);
          System.out.println(p); // call Person toString
          System.out.println(s); // call Student toString
          // Uncomment the code below to test the APStudent class
          /*
          APStudent ap = new APStudent("Ayanna", 1002, 5);
          System.out.println(ap);
          */
      }
  }

  class Student extends Person
  {
      private int id;

      public Student(String name, int id)
      {
          super(name);
          this.id = id;
      }

      public String toString()
      {
          return super.toString() + " " + id;
      }
  }

  class APStudent extends Student
  {
      private int score;

      public APStudent(String name, int id, int score)
      {
          super(name, id);
          this.score = score;
      }
      // Add a toString() method here that calls the super class toString

  }
```
> After trying the code below, complete the subclass called ``APStudent`` that extends ``Student`` with a new attribute called ``APscore`` and override the ``toString()`` method to call the superclass method and then add on the ``APscore``. Uncomment the ``APStudent`` object in the main method to test it.


### ``equals`` Method

One of the important methods inherited from ``Object`` is the ``equals(Object
obj)`` method. This method is used to test if the **current object** and the passed
object called ``obj`` are equal. But what does that mean?

As you can see if you run the code below, the ``equals`` method inherited from
``Object`` only returns ``true`` if the two objects references refer to the same
object. In other words it is does the same test as ``==``.

```java
   public class Person
   {
       private String name;

       public Person(String theName)
       {
           this.name = theName;
       }

       public static void main(String[] args)
       {
           Person p1 = new Person("Kairen");
           Person p2 = new Person("Jewel");
           Person p3 = new Person("Kairen");
           Person p4 = p3;
           System.out.println(p1.equals(p2));
           System.out.println(p2.equals(p3));
           System.out.println(p1.equals(p3));
           System.out.println(p3.equals(p4));
       }
   }
```

![image](Figures/equalsEx.png)

### Overriding the ``equals`` Method

The ``equals`` method defined in ``Object`` and thus inherited by all classes
only considers two object references equivalent if they refer to exactly the
same object. But we saw in Unit 2 that the ``String`` class provides an
``equals`` method that considers two ``String`` objects equivalent if they have
the same characters in the same order, even if they are actually different
objects. How does that work?

It is because the ``String`` class has **overridden** the ``equals`` method it
inherited from ``Object`` to provide a definition of equality that makes more
sense.

As we saw in section 9.3 a class can override inherited methods by providing a
method with the same method signature (method name, parameter types, and return
type). ``String`` has done that with ``equals`` so when we compare ``String``
objects with ``equals`` that new method will be called instead of the inherited
one.

```java
   public class StringTest
   {
       public static void main(String[] args)
       {
           String s1 = "hi";
           String s2 = "Hi";
           String s3 = new String("hi");
           System.out.println(s1.equals(s2));
           System.out.println(s2.equals(s3));
           System.out.println(s1.equals(s3));
       }
   }
```

However, overriding ``equals`` is a bit more involved than overriding
``toString``. While the ``toString`` method is only required to produce a
reasonable human-readable ``String`` representation of an object, ``equals`` has
to meet a more complex set of requirements in order to be useful.


#### 💻 In-Class Activity: Savings Account
{:.no_toc}


<div class="task" markdown="block">
    
1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit9-Inheritance/topic-9-7-Object.html"><button type="button" name="button" class="btn">CSAwesome Topic 9.7</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: Savings Account** activity in pairs.

</div>

---

## ⭐️ Summary

- The ``Object`` class is the superclass of all other classes in Java and a part of the built-in ``java.lang`` package.

- The following ``Object`` class methods are part of the Java Quick Reference:

  - ``String toString()``
  - ``boolean equals(Object other)``

- Subclasses of Object often override the ``toString`` and ``equals`` methods
  with class-specific implementations.

- When overriding ``equals``, it’s important to satisfy all the requirements of
  a correct implementation.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
