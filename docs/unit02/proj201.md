---
layout: project
title: "💻 PROJECT #2.1"
projectname: "MadLibs"
parent: "2️⃣ Using Objects"
nav_order: 10
---

### Overview & Setup

In this project, you'll be creating your own **MadLibs** game using Java! A MadLibs story is a short story where certain words are left out, and players fill in the blanks with their own words (like nouns, verbs, adjectives, etc.), making the story fun and creative. You will write a story, replace some words with variables, and ask the user to fill in those blanks by gathering input using a `Scanner` object.

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

1. Come up with a fun story to use for MadLibs. Yours should be long enough to include at least **10 variables**. Choose nouns, verbs, adjectives, etc., that you want the user to fill in, and decide how many blanks you’ll need.
> _Example:_ "Today, I went to the PLACE to VERB with my ADJECTIVE NOUN. It was a ADJECTIVE day, and we had lots of fun!"
2. In your `main` method, **declare variables** for the parts of the story that the user will input. For each _blank_ in the story, you'll need a variable.
> _Example:_ `String adjective1;`
3. Use a Scanner object to take user input, using the code example below for help.
```java
// Add to TOP of program before the class:
import java.util.Scanner;
// In the main method:
// Construct the Scanner - only do this once
Scanner scan = new Scanner(System.in);
// Take input for each variable!!!
System.out.print("Enter an adjective: ");
adjective1 = scan.nextLine();
```
4. Use string **concatenation** to combine the user's input with your story.
> _Example:_ `String story = "It was a " + adjective1 + " day";`
5. **Print** out your story!
> It may be easier to separate each sentence into its own variable, then use the appropriate method to print them out (either all together or on separate lines). 

</div> 

#### Extensions
* Incorporate **numbers** (`int` and `double`), using the appropriate Scanner class methods to obtain user input, then doing something with the numbers (like printing or using in an expression).
* Add more variables to make your story longer and funnier.
* Format the output to make it look like a paragraph using `\n` for new lines.
* Include emojis to make the story visually interesting!

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
