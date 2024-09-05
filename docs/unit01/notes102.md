---
layout: notes
title: "📓1.2: Printing & Debugging" 
parent: "1️⃣ Primitive Types"
nav_order: 2
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

## Print Methods

Java has two different methods to print **output** to the screen:

- **System.out.println(value)** : prints the value followed by a new line (ln)
- **System.out.print(value)** : prints the value without advancing to the next line

``System.out.println("Hi there!");`` prints out the characters between the first ``"`` and the second ``"`` followed by a new line.  

#### String Literals
{:.no_toc}

The ``"Hi there!"`` is called a **string literal**, and it can have zero to many characters enclosed in starting and ending double quotes.

### Syntax: the "grammar" of Java
Special words—also called **keywords**—such as ``public``, ``class``, and ``if`` must be in lowercase, but class names such as ``System`` and ``String`` are capitalized. 

Lines in a Java program that express a _complete action_ such as assigning a value to a variable must end with a semicolon (``;``). Such a line is called a **statement**. You can think of the semicolon (``;``) in Java like a period (``.``) in English. The same way you use a period to end a sentence in English, you use a semicolon to end a statement in Java.  

> You will not be penalized on the AP exam if you forget a needed semicolon but the Java compiler is not so lenient; your program won't compile without it.
>
> Note also that not *every* line ends with a semicolon; if the line starts a **construct** like an `if` statement, there is no semicolon before the opening ``{`` nor one after the closing ``}``.

### Syntax Errors & Debugging
Computers don't actually speak Java so we have to **compile** (translate) Java source files that we write into class files which is code that a computer can understand and run. 

**Syntax errors** are reported to you by the compiler if your Java code is not correctly written. Examples of syntax errors are a semicolon ``;`` missing or if the code has a open curly brace ``{`` or open quote ``"``, but no close curly brace ``}`` or close quote ``"``. Informally, a syntax error is called a **bug**, and the process of removing errors is called **debugging**. An early computer science pioneer [Grace Hopper](https://en.wikipedia.org/wiki/Grace_Hopper) documented a real bug, a moth that flew into a computer in 1947!

The compiler tries to run your code, but if your code has **syntax errors**, you will see error messages displayed below the code. Compiler error messages will tell the line number that the compiler found the error and the type of error.  The error messages are not always easy to understand and sometimes the actual error is before the line that the compiler says is the problem.

Debugging is a normal part of coding. It can be frustrating at times, but you will get better at it with practice! Sometimes another pair of eyes really helps, so ask a friend if you get stuck or try explaining your code line by line to someone or even a rubber duck. [Rubber duck debugging](https://rubberduckdebugging.com/) is a lot of fun!

### Reading Error Messages
{:.no_toc}

Oops! Your code has an error. Before you try to fix it, read the error message.  you try to fix an error, look for the error
message. It will be a lot easier to find the problem, and other problems like it, if you
understand how to read the error message. 

The example below is an example of a **compile time error** - it is an
error detected by the compiler.

```
   FirstClass.java:5: error: unclosed string literal
          System.out.println("Hi there!);
                             ^
   1 error
```

The first line starts with the name of the file that was being compiled.
Because you submitted your code via this web page you didn't actually name
the file but it was named for you to match the name of your class. Then
there's a colon (``:``) followed by a number. That number tells you the line
number in the file where the compiler detected the error, in this case
line 5.

Error messages aren't always 100% accurate about where the error actually is;
sometimes you actually need to change something a bit earlier in the program
and sometimes a bit later. But the line number is the best place to start
looking.

After the line number and another colon, you will find the actual error message. These
can be kind of cryptic but you should still read it. As you learn more Java
vocabulary they will become more meaningful but they almost always contain
some useful clues. For instance take this error message: “unclosed string
literal”. You may not know what a string literal is (yet) but “unclosed”
suggests something was opened and then not closed. Keep that thought in mind.

Now look at the next two lines. The very next line is just the line of code
from your program. But below that is a very important line containing a
single caret (``^``) positioned to point at exactly where in the line the
Java compiler thinks the problem is. In this case it’s pointing at the
quotation mark (``”``) before “Hi”. So it’s complaining about something being
unclosed and it’s pointing us at a quotation mark. Usually quotation marks
come in pairs called the open quote and the close quote, right? And if you
look at the line of code you’ll see that there’s no closing quotation mark.
Could that be the problem? 

### Comments

In Java and many text-based coding languages, ``//`` is used to mark the
beginning of a comment. For multi-line comments, use ``/*`` to start the comment
and ``*/`` to end the comment. The compiler will _skip over comments_. However, it
is a good idea to use comments to make notes to yourself and other programmers
working with you. 

Here are some examples of good commenting:

```java
/* MyClass.java
   Programmer: My Name
   Date:
*/

// Keep track of the max score
int max = 10; 
```

---

## ⭐️ Summary

- A Java program starts with `public class ClassName { }`. If you are using your own files for your code, each class should be in a separate file that matches the class name inside it, for example `NameOfClass.java`.
- Most Java classes have a main method that will be run automatically. It looks like this: `public static void main(String[] args) { }`.
- The `System.out.print()` and `System.out.println()` methods display information given inside the parentheses on the computer monitor.
- `System.out.println()` moves the cursor to a new line after the information has been displayed.
- A **string literal** is enclosed in double quotes (`` " " ``).
- Java statements end in ``;`` (semicolon). ``{ }`` are used to enclose blocks of code. ``//`` and ``/* */`` are used for comments.
- A **compiler** translates Java code into a class file that can be run on your computer.
- **Compiler or syntax errors** are reported to you by the compiler if the Java code is not correctly written. Some things to check for are ``;`` at end of lines containing complete statements and matching ``{ }``, ``( )``, and ``" "``.


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
