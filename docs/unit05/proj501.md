---
layout: project
title: "💻 PROJECT #5.1"
projectname: "Creature Class"
parent: "5️⃣ Writing Classes"
nav_order: 11
---

### Overview & Setup

In this project, you will practice defining and working with Java classes by creating an interactive `Creature` class. You'll demonstrate their understanding of instance variables, constructors, getter and setter methods, the toString method, and behavior methods.

<div class="setup" markdown="block">

1. Go to the `CS2 Project 5.1` assignment on **Blackbaud** and follow the provided **GitHub Classroom** link.
  > 📁 Clicking the link generates a **private repository** for your project with the appropriate starter code. Note that **projects** are stored within the [BWL-CS Organization](https://github.com/BWL-CS), so you _cannot_ access it from the "Your Repositories" page!
2. Open the repository in a **Codespace** whenever you spend time working on the program, in class or at home. 
  > ⚠️ Always remember to `commit changes` after every coding session!
3. When your project is complete, submit the link to your **repository page** (*not the Codespace!*) in the `CS2 Project 5.1` assignment on Blackbaud.

</div>

### Instructions & Requirements

<div class="task" markdown="block">

1. **Create the Class**
  - Create a new _file_ named `Creature.java`.
  - Define a `public` _class_ named `Creature`.
2. **Declare Instance Variables**
  - Add the following instance variables:
    - `private String species;` (_required_)
    - At least one other `String` variable
    - At least one `int` variable 
    - At least one `double` variable
    - At least one `boolean` variable
  > Make sure all instance variables are `private`!
3. **Write Two Constructors**
  - Write a _no-argument_ constructor that sets _default_ values for all instance variables.
  - Write a _parameterized_ constructor that initializes all instance variables based on _arguments_ passed to it.
  > Make sure to use the `this` keyword!
4. **Write Accessor/Getter Methods**
  - Write a `public` _get_ method for each instance variable to allow external access to their values.
  > Make sure your `return` type matches the instance variable!
5. **Write Mutator/Setter Methods**
  - Write a `public` _set_ method for each instance variable to allow external modification of their values.
  > Make sure your method accepts a _parameter_ of the same data type as the instance variable!
6. **Write a toString Method**
  - Override the `toString()` method to `return` a _String representation_ of the object that includes all instance variables.
7. **Write Behavior Methods**
  - Add at least TWO additional behavior methods that define _actions_ the creature can perform. These methods can use the instance variables and return results, perform tasks, or indirectly affect the state of instance variables.
  - _Examples:_
    - `public void grow(int years)` - Increases the age of the creature by a given number of years.
    - `public String speak()` - Returns a string like "The Dragon lets out a mighty roar!" based on the species.
8. **Write a Test Class**
  - Create a separate `Main.java` class with a main method that demonstrates all features of your Creature class.
  - In the `main()` method:
    - Create at least two Creature _objects_ using different constructors.
    - Use the _getter_ and _setter_ methods to access and modify their instance variables.
    - Call the _behavior methods_ and display their outputs.
    - _Print_ the objects using the toString method.

</div> 

### Extension

{:.highlight}
Turn your text-based version into a visual one with a **GUI** (Graphical User Interface)! See my `Java Swing` demo: [GitHub Swing GUI](https://github.com/katerinanavab/JavaGUI-Demo)

