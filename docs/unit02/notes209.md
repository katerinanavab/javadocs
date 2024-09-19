---
layout: notes
title: "📓2.9: The Math Class" 
parent: "2️⃣ Using Objects"
nav_order: 9
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 2.9](https://runestone.academy/ns/books/published/csawesome/Unit2-Using-Objects/topic-2-9-Math.html?mode=browsing) 

<div class="setup" markdown="block">

📝 Take notes in a **Codespace** during class, coding along with the instructor.

1. Go to GitHub and click on your picture in the _TOP RIGHT_ corner
2. Select `Your repositories`
3. Open `CS2-Unit-2-Notes`
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` (unless you already have one listed there), wait for the environment to load, _then you're ready to code_!

</div>

## Using the Math Class

Games would be boring if the same thing happened each time you played the game.  Random numbers can be used in games to generate different outcomes each time the game is played. In Java, the ``Math.random()`` method to is used to generate a random number.

There are lots of mathematical methods in the ``Math`` class
that you might want to use in your programs, like ``Math.pow(2,3)`` which calculates the 2 to the power of 3 which is 8.

These methods are in the **Math** class defined in the java.lang package. These are **static methods** which means you can call them by just using ``ClassName.methodName()`` without creating an object.
This is why we can just say Math.random() instead of having to define an object of the class Math.


{:.highlight}
**Static methods** (also called class methods) are called using the class name and the dot operator (.) followed by the method name. You do not need to create an object of the class to use them. You can use ClassName.methodName() or just methodName() if they are called from within the same class.

### Mathematical Functions



---

## ⭐️ Summary

- Static Math methods can be called using **Math**.method(); for each method.

- The following static Math methods are part of the Java Quick Reference:

  - **int abs(int)** : Returns the absolute value of an int value (which means no negatives).
  - **double abs(double)** : Returns the absolute value of a double value.
  - **double pow(double, double)** : Returns the value of the first parameter raised to the power of the second parameter.
  - **double sqrt(double)** :  Returns the positive square root of a double value.
  - **double random()** :  Returns a double value greater than or equal to 0.0 and less than 1.0 (not including 1.0)!

- The values returned from Math.random can be manipulated to produce a random int or double in a defined range.

- **(int)(Math.random()*range) + min** moves the random number into a range starting from a minimum number. The range is the **(max number - min number + 1)**. For example, to get a number in the range of 5 to 10, use the range 10-5+1 = 6 and the min number 5: ``(int)(Math.random()*6) + 5``.

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
