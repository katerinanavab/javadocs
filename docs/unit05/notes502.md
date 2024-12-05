---
layout: notes
title: "📓5.2: Constructors" 
parent: "5️⃣ Writing Classes"
nav_order: 2
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 5.2](https://runestone.academy/ns/books/published/csawesome/Unit5-Writing-Classes/topic-5-2-writing-constructors.html?mode=browsing) 

---

## Writing Constructors

In Unit 2, we learned how to create objects by calling **constructors**. To
review, a call to a constructor consists of the word ``new`` followed by the
name of the class being constructed, and then an argument list in parentheses.
For example, here is how we create ``World``, ``Turtle``, and ``Person``
objects.

```java

    // To create a new object, write:
    // ClassName variableName = new ConstructorName(arguments);
    World world = new World();
    Turtle t = new Turtle(world);
    Person p = new Person("Pat", "pat@gmail.com", "123-456-7890");
```

Now it's time to learn to write our own constructors.

### Constructor Signature

In the source code for a class, constructors are usually written after the
instance variables and before any methods.

The signature of a constructor is similar to the signature of a method except
there is no return type, not even ``void``, and instead of a method name, the
name of the constructor is the same as the name of the class. The constructors
you write will almost always be marked ``public``. Like methods, constructors
also have a **parameter list** specified in parenthesis that declare the
variables that will be used to hold the arguments passed when the constructor is
called.

```java

   public class ClassName
   {
       /* Instance variable declarations go here, before constructors */

       /* Constructor - same name as Class, no return type */
       public ClassName()
       {
           /* Implementation not shown */
       }

       /* Method definitions go here, after constructors */
   }
```

{:.highlight}
⚠️ Constructors must have the **same name** as the `class`! Constructors have **no return type**!

### The Job of a Constructor

The job of a constructor is to set the initial values for the object’s instance
variables to useful values. But what does “useful” mean? Sometimes we describe
the values of all an object's instance variables at a given time as the object's
**state**. And we say an object is in a **valid state** when all its instance
variables have values that let us use the object by invoking its public methods.
So another way to describe the job of a constructor is to set the object’s
instance values so it’s in a valid state and ready to be used.

Classes can have zero or more constructors but they should all produce an object
in a valid state.

The easiest way to write a constructor is to *not* write one. If you do not
write a constructor your class will automatically get what is called the
**default no-argument constructor**. This constructor will initialize all your
instance variables to the default value for their type: 0 for ``int`` and
``double``, ``false`` for ``boolean``, and ``null`` for all reference types. If
those default values are sufficient to put your object into a valid state you may
not need to write a constructor at all.

Usually, however, if you are writing a class that has instance variables, you
need to initialize your instance values to some other values. In that case you
probably need to write a constructor that takes arguments and uses them to
initialize your instance variables.

For example, consider the constructor from the ``Person`` class from the last
section.

```java

   public Person(String initName, String initEmail, String initPhone)
   {
       name = initName;
       email = initEmail;
       phoneNumber = initPhone;
   }
```

This constructor ensures that all three of the instance variables (``name``, ``email``, and ``phoneNumber``) in ``Person`` 
are initialized to the values provided by whatever code called the constructor. For example, in the constructor call  
``new Person("Pat", "pat@gmail.com", "123-456-7890")``, the argument "Pat" is passed into the parameter variable ``initName``, 
which the constructor then assigns to the instance variable ``name``.  

One important note: if you do write a constructor, Java will not generate the
default constructor for you. This is a good thing because it lets you make sure
that instances of your class are always properly initialized. With this
constructor in place, for instance, there’s no way to construct a ``Person``
object without providing the three required ``String`` values.

Sometimes you will want to write more than one constructor so there are
different ways of making an instance of your class. One reason to do that is to
make it convenient to create instances from different kinds of arguments. This
is called **overloading** and we discussed it in Chapter 2 from the perspective
of calling constructors.

For instance, suppose we were writing a program that had another class
``AddressBookEntry`` which had getters for name, email, and phone number. In
that program it might be useful to write another ``Person`` constructor like
this:

```java

   public Person(AddressBookEntry address) {
   {
       name = address.getName();
       email = address.getEmail();
       phoneNumber = address.getPhoneNumber();
   }
```

Sometimes you might still even want to provide a no-argument constructor. If
there’s a valid object that you can create without any arguments, you could
write a no-argument constructor for ``Person`` like:

```java

   public Person()
   {
       name = "Anonymous";
       email = "unknown";
       phoneNumber = "unknown";
   }
```

It’s up to you to decide if this is actually a useful value to have or if it
would be better to force the users of the ``Person`` class to choose the
values themselves.

#### 💻 In-Class Activity: Student Class
{:.no_toc}


<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit5-Writing-Classes/topic-5-2-writing-constructors.html?mode=browsing"><button type="button" name="button" class="btn">CSAwesome Topic 5.2</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: Student Class** activity in pairs.

</div>

---

## ⭐️ Summary

- **Constructors** are used to set the initial state of an object, which includes initial values for all instance variables.

- When no constructor is written, Java provides a no-argument **default constructor**, and the instance variables are set to their default values (0 for ``int`` and ``double``, ``null`` for objects like ``String``).

- Constructor parameters are local variables to the constructor and provide data to initialize instance variables.
  

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
