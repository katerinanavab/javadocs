---
layout: notes
title: "📓5.9: this Keyword" 
parent: "5️⃣ Writing Classes"
nav_order: 9
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 5.9](https://runestone.academy/ns/books/published/csawesome/Unit5-Writing-Classes/topic-5-9-this.html?mode=browsing) 

---

## this Keyword

The keyword ``this`` can be used in a class to refer to the current calling object.

For example, in the following Class Person, when we create an object p1 and call the constructor or p1.setEmail(), the word "this" refers to p1. And when we make the same method calls with object p2, "this" refers to p2.
Run the code below and also check it out in the Java visualizer with the Show CodeLens button which shows how this refers to different objects when the code is run.


Observe the use of the keyword this in the code below. Click on the CodeLens button and then forward to see the memory in action.
```java
  public class Person
  {
      // instance variables
      private String name;
      private String email;
      private String phoneNumber;

      // constructor
      public Person(String theName)
      {
          this.name = theName;
      }

      // accessor methods - getters
      public String getName()
      {
          return this.name;
      }

      public String getEmail()
      {
          return this.email;
      }

      public String getPhoneNumber()
      {
          return this.phoneNumber;
      }

      // mutator methods - setters
      public void setName(String theName)
      {
          this.name = theName;
      }

      public void setEmail(String theEmail)
      {
          this.email = theEmail;
      }

      public void setPhoneNumber(String thePhoneNumber)
      {
          this.phoneNumber = thePhoneNumber;
      }

      public String toString()
      {
          return this.name + " " + this.email + " " + this.phoneNumber;
      }

      // main method for testing
      public static void main(String[] args)
      {
          Person p1 = new Person("Sana");
          System.out.println(p1);
          Person p2 = new Person("Jean");
          p2.setEmail("jean@gmail.com");
          p2.setPhoneNumber("404 899-9955");
          System.out.println(p2);
      }
  }
```

Note that in the code above, this.name, this.email, and this.phoneNumber are equivalent to writing just name, email, and phoneNumber, but ``this.variable`` is a way to indicate that we are referring to the instance variables of this object instead of a local variable.

Static methods cannot refer to this or instance variables because they are called with the classname, not an object, so there is no this object.


The keyword this is sometimes used by programmers to distinguish between variables. Programmers can give the parameter variables the same names as the instance variables and this can distinguish them and avoid a naming conflict. For example, both the instance variable and the parameter variable are called name in the code below.

.. code-block:: java

     // instance variables
     private String name;

     // constructor
     public Person(String name)
     {
        // Set this object's instance variable name to the parameter variable name
        this.name = name;
     }

The ``this`` variable can be used anywhere you would use an object variable.  You can even pass it to another method as an argument. Consider the classes below, ``Pay`` and ``Overtime``. The ``Pay`` class declares an ``Overtime`` object and passes in ``this`` (the current ``Pay`` object) to its constructor which computes the overtime with respect to that ``Pay`` object. Try this code in the active code exercise below with the Show CodeLens button to trace through it step by step. Here is an image that shows how ``this``, ``myPay`` and ``p`` all refer to the same object in memory.

![image](Figures/thisTrace.png)

What does this code print out? Trace through the code with the Show CodeLens button. Notice how the this Pay object is passed to the Overtime constructor.

```java
   public class Pay
   {
       private double pay;

       public Pay(double p)
       {
           pay = p;
       }

       public double getPay()
       {
           return pay;
       }

       public void calculatePayWithOvertime()
       {
           // this Pay object is passed to the Overtime constructor
           Overtime ot = new Overtime(this);
           pay = ot.getOvertimePay();
       }

       public static void main(String[] args)
       {
           Pay myPay = new Pay(100.0);
           myPay.calculatePayWithOvertime();
           System.out.println(myPay.getPay());
       }
   }

   class Overtime
   {
       private double payWithOvertime;

       public Overtime(Pay p)
       {
           payWithOvertime = p.getPay() * 1.5;
       }

       public double getOvertimePay()
       {
           return payWithOvertime;
       }
   }
```

#### 💻 In-Class Activity: Bank Account
{:.no_toc}


<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit5-Writing-Classes/topic-5-9-this.html?mode=browsing"><button type="button" name="button" class="btn">CSAwesome Topic 5.9</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: Bank Account** activity in pairs.

</div>

---

## ⭐️ Summary

- Within a non-static method or a constructor, the keyword `this` is a reference to the **current object**, the object whose method or constructor is being called.

- `this.instanceVariable` can be used to distinguish between this object's instance variables and local parameter variables that may have the same variable names.

- **Static methods** do not have a `this` reference.

- The `this` variable can be used anywhere you would use an object variable, even to pass it to another method as an argument.
  

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
