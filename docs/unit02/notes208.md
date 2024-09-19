---
layout: notes
title: "📓2.8: Wrapper Classes" 
parent: "2️⃣ Using Objects"
nav_order: 8
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 2.8](https://runestone.academy/ns/books/published/csawesome/Unit2-Using-Objects/topic-2-8-IntegerDouble.html?mode=browsing) 

<div class="setup" markdown="block">

📝 Take notes in a **Codespace** during class, coding along with the instructor.

1. Go to GitHub and click on your picture in the _TOP RIGHT_ corner
2. Select `Your repositories`
3. Open `CS2-Unit-2-Notes`
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` (unless you already have one listed there), wait for the environment to load, _then you're ready to code_!

</div>

## Wrapper Classes: Integer and Double

For every primitive type in Java, there is a built-in object type called a wrapper class. The wrapper class for int is called Integer, and for double it is called Double.   Sometimes you may need to create a wrapped object for a primitive type so that you can give it to a method that is expecting an object. To wrap a value, call the constructor for the wrapper class in earlier versions of Java. In Java 9 on, this is **deprecated** which means it's not the best way to do this anymore, and you should instead just set it equal to a value. The AP CSA Exam covers Java 7 which does allow using the constructor.

```java
   // in older versions of Java (and on the AP exam)
   Integer i = new Integer(2); // create an object with 2 in it
   Double d = new Double(3.5); // create an object with 3.5 in it

   // in newer versions of Java (9+)
   Integer i = 2;
   Double d = 3.5;
```

These wrapper classes (defined in the `java.lang` included **package**) are also useful because they have some special values (like the minimum and maximum values for the type) and methods that you can use.

When would you ever use `Integer.MIN_VALUE` or `Integer.MAX_VALUE`?  They are handy if you want to initialize a variable to the smallest possible value and then search a sequence of values for a larger value.

### Autoboxing and Unboxing 

**Autoboxing** is the automatic conversion that the Java compiler makes between primitive types and their corresponding object wrapper classes. This includes converting an `int` to an `Integer` and a `double` to a `Double`. The Java compiler applies autoboxing when a primitive value is passed as a parameter to a method that expects an object of the corresponding wrapper class or assigned to a variable of the corresponding wrapper class. Here's an example of autoboxing.

```java
   Integer i = 2;
   Double d = 3.5;
```

**Unboxing** is the automatic conversion that the Java compiler makes from the wrapper class to the primitive type. This includes converting an Integer to an int and a Double to a double. The Java compiler applies unboxing when a wrapper class object is passed as a parameter to a method that expects a value of the corresponding primitive type or assigned to a variable of the corresponding primitive type. Here's an example of unboxing:

```java
   Integer i = 2;  // autoboxing - wrap 2
   int number = i; // unboxing - back to primitive type
```

---

## ⭐️ Summary

- The `Integer` class and `Double` class are **wrapper classes** that create objects from primitive types.

- The following `Integer` **methods** and **constructors**, including what they do and when they are used, are part of the Java Quick Reference.

  - `Integer(value)`: Constructs a new Integer object that represents the specified int value.
  - `Integer.MIN_VALUE` : The minimum value represented by an int or Integer.
  - `Integer.MAX_VALUE` : The maximum value represented by an int or Integer.
  - `int intValue()` : Returns the value of this Integer as an int.

- The following `Double` **methods** and **constructors**, including what they do and when they are used, are part of the Java Quick Reference Guide given during the exam:

  - `Double(double value)` : Constructs a new Double object that represents the specified double value.
  - `double doubleValue()` : Returns the value of this Double as a double.

- **Autoboxing** is the automatic conversion that the Java compiler makes between primitive types and their corresponding object wrapper classes. This includes converting an int to an Integer and a double to a Double.

- The Java compiler applies autoboxing when a primitive value is:

  - Passed as a parameter to a method that expects an object of the corresponding wrapper class.
  - Assigned to a variable of the corresponding wrapper class.

- **Unboxing** is the automatic conversion that the Java compiler makes  from the wrapper class to the primitive type. This includes converting an Integer to an int and a Double to a double.

- The Java compiler applies unboxing when a wrapper class object is:

  - Passed as a parameter to a method that expects a value of the corresponding primitive type.
  - Assigned to a variable of the corresponding primitive type.


<br>

<div class="warn" markdown="block">

🛑 When class ends, don't forget to **SAVE YOUR WORK**!

1. Navigate to the `Source Control` menu on the _LEFT_ sidebar
2. Click the <button type="button" name="button" class="btn btn-green">commit changes</button> button on the _LEFT_ menu
3. Type a brief **commit message** at the top of the file that opens, for example: `updated Main.java`
4. Click the small `✔️` **checkmark** in the _TOP RIGHT_ corner
5. Click the <button type="button" name="button" class="btn btn-green">sync changes</button> button on the _LEFT_ menu
6. _Finally you can close your Codespace!_

</div>

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
