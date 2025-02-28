---
layout: notes
title: "📓9.2: Constructors" 
parent: "9️⃣ Inheritance"
nav_order: 2
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 9.2](https://runestone.academy/ns/books/published/csawesome/Unit9-Inheritance/topic-9-2-constructors.html) 

---

## Inheritance and Constructors

Subclasses inherit ``public`` methods from the superclass that they extend, but
they cannot access the ``private`` instance variables of the superclass
directly. And subclasses do not inherit constructors from the superclass. But
inherited instance variables need to be properly initialized or none of the
inherited methods are likely to work properly, so how can a subclass initialize
the superclass's ``private`` variables?

If the super class provides ``public`` setter methods for those variables the
subclass could use those. But that won't always be the case. And sometimes
constructors do more complex initialization than just setting variables.

### The `super` Keyword

The way out is provided by the keyword ``super``. When used like the name of a
method, i.e. when followed with parentheses and arguments, ``super`` provides a
way to call the code in a superclass constructor, passing whatever arguments it
needs. But unlike when we call a constructor with ``new``, a call to ``super``
doesn't create a new object. Instead it runs the constructor’s code in the
context of the object currently being constructed. This lets the superclass
constructor initialize the instance variables declared in the superclass
including ``private`` variables the subclass can’t directly access.

It’s critical that all the instance variables in an object be properly
initialized before the object is used, including by code in the rest of the
constructor. To ensure that, if the constructor doesn’t start with a call to
``super`` Java will automatically insert a call to ``super`` with no arguments.
(That means if the superclass does not have a no-argument constructor that the
subclasses will have to explicitly call ``super`` with the appropriate arguments
for some constructor that does exist. This ensures that instances of the
subclass are properly initialized.)

For example the call to ``super(theName)`` in ``Employee`` below runs the code
in the ``Person`` constructor that takes a ``String`` argument which presumably
initializes an instance variable in the ``Person`` class to hold the name.

```java
public class Employee extends Person {
    public Employee(String theName) {
        super(theName); // calls Person(String) constructor
    }
}
```

### Chain of Initialization

As you may recall from Unit 5, if you do not write a constructor your class will
automatically get a default no-argument constructor. In addition to initializing
all instance variables to the default value for their type, the default
no-argument constructor calls the superclass's no-argument constructor.

This means you can only write a class with a default no-argument constructor if
its superclass has a no-argument constructor. If you are extending a class
without a no-argument constructor but you want your class to have a no-argument
constructor you will need to explicitly write one and use ``super`` to call an
existing constructor on the superclass with appropriate arguments.

However it is created, explicitly or implicitly, the chain of ``super`` calls
from each subclass to its superclass ends in the no-argument constructor of
``java.lang.Object``. This is a special class defined in Java which is the superclass
of any class that doesn’t explicitly ``extend`` some other class and the only
class with no superclass and thus no ``super`` constructor that needs to be
called.

#### 💻 In-Class Activity: Square is-a Rectangle
{:.no_toc}


<div class="task" markdown="block">
    
1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit9-Inheritance/topic-9-2-constructors.html"><button type="button" name="button" class="btn">CSAwesome Topic 9.2</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: Square is-a Rectangle** activity in pairs.

</div>

---

## ⭐️ Summary

- Subclasses do **NOT have access** to the ``private`` instance variables in a superclass that they extend.

- Constructors are **NOT inherited**.

- A superclass **constructor** must be called from the first line of a subclass constructor by using the keyword ``super`` and passing appropriate parameters.
  - If there is no explicit call to ``super``, an implicit call to ``super()`` will be added by the Java compiler.
  - Regardless of whether the superclass constructor is called implicitly or explicitly, the process of calling superclass constructors continues until the ``Object`` constructor is called. At this point, all of the constructors within the hierarchy execute beginning with the ``Object`` constructor.

- The **actual parameters** passed in the call to ``super`` provide values that the **superclass constructor** can use to _initialize_ the object’s instance variables.


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
