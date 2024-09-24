---
layout: project
title: "💻 PROJECT #2.1"
projectname: "MadLibs"
parent: "2️⃣ Using Objects"
nav_order: 10
---

### Overview & Setup

Have you ever played MAD LIBS? In this game, you first choose a bunch of words without looking at the story, and then those words are filled into the story to make it sound very wacky!

<div class="setup" markdown="block">

1. Go to the `CS2 Project 2.1` assignment on **Blackbaud** and follow the provided **GitHub Classroom** link.
  > 📁 Clicking the link generates a **private repository** for your project with the appropriate starter code. Note that **projects** are stored within the [BWL-CS Organization](https://github.com/BWL-CS), so you _cannot_ access it from the "Your Repositories" page!
2. Open the repository in a **Codespace** whenever you spend time working on the program, in class or at home. 
  > ⚠️ Always remember to `commit changes` after every coding session!
3. When your project is complete, submit the link to your **repository page** (*not the Codespace!*) in the `CS2 Project 2.1` assignment on Blackbaud.

</div>

### Instructions & Requirements

#### PART A: Create a MadLibs Story
<div class="task" markdown="block">

1. Come up with a fun story to use for MadLibs. Yours should be at least **10 sentences** long. Choose nouns, verbs, adjectives, etc., that you want the user to fill in, and decide how many blanks you’ll need.
> Example: "Today, I went to the PLACE to VERB with my ADJECTIVE NOUN. It was a ADJECTIVE day, and we had lots of fun!"

2. In your `main` method, **declare variables** for the parts of the story that the user will input. For each _blank_ in the story, you'll need a variable.
> Example: `String adjective1;`

3. Use a Scanner object to take user input, using the code example below for help.
```java
// Only need to construct the Scanner once
Scanner scan = new Scanner(System.in);

// Do this for each variable!!!
System.out.print("Enter an adjective: ");
adjective1 = scan.nextLine();
```
4. Use string **concatenation** to combine the user's input with your story.
> Example: `String story = "It was a " + adjective1 + " day";`

5. Print out your story!
> It may be easier to separate each sentence into its own variable, then use the appropriate method to print them out (either all together or on separate lines). 

</div> 

#### PART B: Practice String Methods

#### Reminders
* Strings in Java are **objects** of the `String` class that hold _sequences of characters_.
* String objects can be created by using **string literals** (`String s = “hi”;`) or by calling the String class constructor (`String t = new String(“bye”);`).
* String objects can be **concatenated** using the `+` or `+=` operator, resulting in a new String object.
* Primitive values can be **concatenated** with a String object. _This causes implicit conversion of the values to String objects._

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from []().
{: .fs-2 }
