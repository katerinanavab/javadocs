---
layout: notes
title: "📓9.3: Overriding" 
parent: "9️⃣ Inheritance"
nav_order: 3
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 9.3](https://runestone.academy/ns/books/published/csawesome/Unit9-Inheritance/topic-9-3-overriding.html) 

---

## Overriding Inherited Methods

A subclass inherits all public methods from its superclass, and these methods remain public in the subclass. But, we also usually add more methods or instance variables to the subclass. Sometimes, we want to modify existing inherited methods. This is called **overriding** methods.

**Overriding** an inherited method means providing a public method in a subclass with the same **method signature** (method name, parameter type list and return type) as a public method in the superclass.  The method in the subclass will be called *instead of* the method in the superclass. One method that is frequently overridden is the ``toString`` method. 

{:.important}
To **OVERRIDE** an inherited method, the method in the _child class_ must have the **same signature** (_name_, _parameter list_, and _return type_) as the _parent method_. 

In the following example the ``MeanGreeter`` inherits the ``greet()`` method from ``Greeter``, but then overrides it.

```java
public class Greeter {
   public String greet() {
      return "Hi";
   }
}
```
```java
public class MeanGreeter extends Greeter {
   public String greet() {
      return "Go Away";
   }
}
```
> 💻 **TRY IT OUT:** Add another subclass called `SpanishGreeter` (or another language that you know) that extends `Greeter` and override the `greet()` method to return ``Hola!`` (or hi in another language) instead of ``Hi!``.

Then a `main` method, you can create an _object_ instance of each class to test out **overriding behavior**: 

```java
   public static void main(String[] args) {
      Greeter g1 = new Greeter();
      System.out.println(g1.greet());
      Greeter g2 = new MeanGreeter();
      System.out.println(g2.greet());
   }
```

Sometimes, you may see the `@Override` annotation above a method. This is optional but it provides an _extra compiler check_ that you have matched the method signature exactly.

```java
@Override
public String greet() {
    return "Go Away";
}
```

### Overloading Methods

Don't get **overriding** a method confused with **overloading** a method! **Overloading** a method is when several methods have the same name but the parameter types, order, or number are different. 

So with overriding, the method signatures look identical but they are in different classes, but in overloading, only the method names are identical and they have different parameters.

```java
    // overriding methods
    g2.greet(); // This could be calling an overridden greet method in g2's class
    g1.greet("Sam"); // This calls an overloaded greet method
```

{:.highlight}
To overload a method the method must have the same name, but the parameter list must be different in some way. It can have a different number of parameters, different types of parameters, and/or a different order for the parameter types. The return type can also be different but you can't have two methods that differ only in their return type.

### Inherited Get/Set Methods

Inheritance means that an object of the child class automatically includes the instance variables and methods defined in the parent class.  But if the inherited instance variables are private, which they should be, the child class can not directly access the them using dot notation.  The child class can use public **accessors** (also called getters or get methods) which are methods that get instance variable values and public **mutators**  (also called modifier methods or setters or set methods) which set their values.

For example, if a parent class has a private instance variable, ``name``, then the parent will often provide a public ``getName`` method and a public ``setName`` method as shown below.

```java
  class Person
  {
      private String name;

      public String getName()
      {
          return name;
      }

      public void setName(String name)
      {
          this.name = name;
      }
  }

  public class Employee extends Person
  {

      private static int nextId = 1;
      private int id;

      public Employee()
      {
          id = nextId;
          nextId++;
      }

      public int getId()
      {
          return id;
      }

      public static void main(String[] args)
      {
          Employee emp = new Employee();
          emp.setName("Dina");
          System.out.println(emp.getName());
          System.out.println(emp.getId());
      }
  }
```

#### 💻 In-Class Activity: Pet Sounds
{:.no_toc}


<div class="task" markdown="block">
    
1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit9-Inheritance/topic-9-3-overriding.html"><button type="button" name="button" class="btn">CSAwesome Topic 9.3</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: Pet Sounds** activity in pairs.

</div>

---

## ⭐️ Summary

- Method **overriding** occurs when a public method in a subclass has the same method signature as a public method in the superclass.

- Any method that is called must be defined within its own class or its superclass.

- A subclass is usually designed to have modified (overridden) or additional methods or instance variables.

- A subclass will inherit all public methods from the superclass (for example all the set and get methods); these methods remain public in the subclass.

- **Overloading** a method is when several methods have the same name but the parameter types, order, or number are different.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
