---
layout: notes
title: "📓4.3: Loops & Strings" 
parent: "4️⃣ Iteration"
nav_order: 3
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 4.3](https://runestone.academy/ns/books/published/csawesome/Unit4-Iteration/topic-4-3-strings-loops.html?mode=browsing) 

<div class="setup" markdown="block">

📝 Take notes in a **Codespace** during class, coding along with the instructor.

1. Go to GitHub and click on your picture in the _TOP RIGHT_ corner
2. Select `Your repositories`
3. Open `CS2-Unit-4-Notes`
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` (unless you already have one listed there), wait for the environment to load, _then you're ready to code_!

</div>

---

## Loops & Strings

Loops are often used for **String Traversals** or **String Processing** where the code steps through a string character by character. In topic 2.6 and 2.7, we learned to use `String` **objects** and built-in string **methods** to process strings. In this lesson, we will write our own **loops** to process strings.

<div class="imp" markdown="block">

Remember that `String` objects are a **sequence of characters** where each character is stored at an **index** (_position_) starting from `0`:

![image](Figures/stringIndicies.png)

🔄 **Loops** that process Strings should always start counting from `0`... recall that the _first_ character in a Java `String` is located at **index** `0` and the _last_ character is at `length() - 1`.

</div>

{:.highlight}
The first character in a Java String is at index 0 and the last characters is at **length()** - 1. So loops processing Strings should start at 0!

---

## ⭐️ Summary


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
