---
layout: notes
title: "📓1.1: Intro to Java" 
parent: "1️⃣ Primitive Types"
nav_order: 1
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

## About the AP CS A Exam

This curriculum will prepare you for the _Advanced Placement Computer Science A Exam_ which tests your programming skills in **Java**.

The AP CSA exam is 3 hours long and has two sections: **multiple choice** and
**free response**. You will be given one hour and 30 minutes for each part. The
first part has 40 multiple-choice questions, and the second part has 4 free
response questions where you have to write Java code by hand. 📝 Each part is worth
50% of your grade. During the exam, you will have access to the [AP CSA
Reference Sheet](https://apstudents.collegeboard.org/ap/pdf/ap-computer-science-a-java-quick-reference_0.pdf).

For more information on the exam see the College Board [AP CSA site](https://apstudent.collegeboard.org/apcourse/ap-computer-science-a). The College Board provides a question bank and formative assessment quizzes for each unit online
for registered AP classes.

Also check out this list of [CS Careers](https://apstudents.collegeboard.org/choosing-courses/major-career-results/course/AP-Computer-Science-A) that taking CSA can lead to. Learning
to code is an increasingly important skill that has applications in many
careers!

---

## What is Java?

What do Android phones, Minecraft, and Netflix have in common? They're all programmed in `Java`! Many of the apps you use in an Android phone or tablet are written in Java. Netflix uses Java for some of its software too. Java is a **programming language** that is used worldwide to create software that we all use.

### First Java Program
{:.no_toc}

Every program in Java is written as a **class**. Java is an **object-oriented language** and we'll learn more about classes and objects in Unit 2. Inside the class, there can be a **main method** that starts the program. When you ask the Java run-time to *run* a class, it will always start execution in the main method. 

> You must always name the **file** the same name as the class name with `.java` as the extension.  All code (programs) in Java must be defined inside a class in a source file, and the name of the class must match the file name.


Here is the template for a simple Java program in a file named `MyClass.java`:

```java
public class MyClass
{
    public static void main(String[] args)
    {
        // Put your code here!
    }
}
```

{:.highlight}
In Java every open curly brace ``{`` must have a **matched** close curly brace ``}``.  These are used to start and end class definitions and method definitions.

### Java Development Environments
The tool that we use to compile a Java **source** file into a Java **class** file is called a `compiler`. Most programmers use an **Integrated Development Environment (IDE)** that has the compiler built in and helps you write, compile, run, and debug programs.

#### GitHub Classroom and Codespaces
{:.no_toc}

Github provides many free opportunities for students and teachers (_unlike Replit_). [Github Classroom](https://classroom.github.com/) allows teachers to set up a classroom group based on Github repositories. Github and `git` are widely used in the computer industry, so learning to use it is great experience for students. Github now has a cloud (online) **IDE** called [Codespaces](https://github.com/features/codespaces) which you can use completely free if you join as a school or get approved as a teacher or student. 

_In Codespaces, you can:_
* Start from a **blank template** or a **repository** ("repo")
* Open a `.java` file in the VSCode editor
* Follow prompts to install the **Java Extension Pack**
* Click on the `Run and Debug` (play button ▶️)
* Follow the prompts to install the Java **debugger**
* See the **output** of your code in the `terminal`


#### GitHub Account Setup

<div class="task" markdown="block">

1. **Go to:** [GitHub Sign Up](https://github.com/signup)
2. Enter your `@gbwl.org` **school email** and press `Continue`
3. Create a **password** that you'll remember 
4. Enter a **username** that follows this pattern: `FirstName` `LastInitial` `GradYear`
    > _For example:_ `KaterinaN2014`
    > DO NOT include your entire last name (_privacy reasons_)

</div>


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
