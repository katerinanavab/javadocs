---
layout: notes
title: "📓5.3: Comments" 
parent: "5️⃣ Writing Classes"
nav_order: 3
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 5.3](https://runestone.academy/ns/books/published/csawesome/Unit5-Writing-Classes/topic-5-3-comments-conditions.html?mode=browsing) 

---

## Comments & Conditions

### Writing Useful Comments

Adding comments to your code helps to make it more readable and maintainable. In the commercial world, software development is usually a team effort where many programmers will use your code and maintain it for years. Commenting is essential in this kind of environment and a good habit to develop. Comments will also help you to remember what you were doing when you look back to your code a month or a year from now.

<div class="imp" markdown="block">
  
There are 3 types of **comments** in Java:

1. ``//`` Single line comment
2. ``/*`` Multiline comment ``*/``
3. ``/**`` Documentation comment ``*/``

</div>

The special characters ``//`` are used to mark the rest of the line as a comment in many programming languages.  If the comment is going to be multiple lines, we use ``/*`` to start the comment and ``*/`` to end the comment.

There is also a special version of the multi-line comment, ``/**``  ``*/``, called the documentation comment. Java has a cool tool called [javadoc](https://www.tutorialspoint.com/java/java_documentation.htm) that comes with the [Java JDK](https://www.oracle.com/technetwork/java/javase/downloads/index.html) that will pull out all of these comments to make documentation of a class as a web page.  This tool generates the official Java documentation too, for example for the [String class](http://docs.oracle.com/javase/7/docs/api/java/lang/String.html). Although you do not have to use this in the AP exam, it's a VERY good idea to use the documentation comment in front of **classes**, **methods**, and **instance variables** in case you want to use this tool.

The compiler will _skip over comments_, so they don't affect how your program runs. They are for you, your teacher, and other programmers working with you. Here are some examples of good commenting:

```java
    /**
    * MyClass.java
    * @author My Name
    * @since Date
    * This class keeps track of the max score.
    */
    public class MyClass()
    {
       private int max = 10; // this keeps track of the max score
       /* The print() method prints out the max */
       public print() {  System.out.println(max); 
    }
```

Note that most IDEs will tend to show comments formatted in italics -- to make them easier to spot.

Notice that there are some special tags that you can use in Java documentation. These are not required but many programmers use them. Here are some common tags:

- `@author`  Author of the program
- `@since`   Date released
- `@version` Version of program
- `@param`   Parameter of a method
- `@return`  Return value for a method
  
---

## ⭐️ Summary


  

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
