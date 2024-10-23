---
layout: project
title: "💻 PROJECT #3.1"
projectname: "Adventure"
parent: "3️⃣ Conditionals"
nav_order: 10
---

### Overview & Setup

One of the first games coded for early computers in the 1970s was called [Colossal Cave Adventure](https://en.wikipedia.org/wiki/Colossal_Cave_Adventure). It was a **text-based interactive fiction game** where you had to make your way through an elaborate cave. The program only understood one word or phrase commands like north, south, enter, take, etc. 

You can try [playing adventure](http://www.web-adventures.org/cgi-bin/webfrotz?s=Adventure) recreated online following some of the commands in this [walkthrough](https://adventuregamers.com/walkthrough/full/colossal-cave). Part of the challenge is finding the commands that the code will understand.

In a game like Adventure, `if`, `else if`, and `else` statements can be used to respond to commands from the user like `n`, `s`, `e`, `w`.

![image](Figures/adventure.jpg)

<div class="setup" markdown="block">

1. Go to the `CS2 Project 3.1` assignment on **Blackbaud** and follow the provided **GitHub Classroom** link.
  > 📁 Clicking the link generates a **private repository** for your project with the appropriate starter code. Note that **projects** are stored within the [BWL-CS Organization](https://github.com/BWL-CS), so you _cannot_ access it from the "Your Repositories" page!
2. Open the repository in a **Codespace** whenever you spend time working on the program, in class or at home. 
  > ⚠️ Always remember to `commit changes` after every coding session!
3. When your project is complete, submit the link to your **repository page** (*not the Codespace!*) in the `CS2 Project 3.1` assignment on Blackbaud.

</div>

### Instructions & Requirements

<div class="task" markdown="block">

1. Use the **starter code** below and run the program. This is a very simple adventure game that lets the user move in 4 different directions. Right now, it only lets the user move north.
```java
import java.util.Scanner;
public class Main {
  public static void main(String[] args) {
    Scanner scan = new Scanner(System.in);
    System.out.println("\n\n You are on an island surrounded by water.\n There is a path to the woods to the NORTH, the sea to the SOUTH, and a beach shack to the EAST. \n Which way do you want to go (n,e,s,w)?");
    String command = scan.nextLine();
    if (command.equals("n")) {
        System.out.println("You enter the forest and hear some rustling. \nThere may be tigers here or maybe it's just monkeys.");
    }
    // Add else-ifs for s, e, w, and an else for any other input. Be creative!
    
  }
}
```
2. Add in `else if` statements to go in the directions of "s" for south, "e" for east, "w" for west, and an `else` statement that says "You can't go in that direction". Be creative and come up with different situations in each direction!
3. How many test-cases are needed to _test all branches_ of your code at this point? Write your answer in a **comment**, and try out your test-cases.
4. Next, come up with a **different location** for your adventure. 📝 **PLAN & DRAW YOUR MAP** before coding!
5. Expand the gameplay by adding more branches (**nesting** conditional blocks).
> * You do not need to keep the commands as `n`, `s`, `e`, `w` every time. Just make sure you tell the user what the options are!
> * Follow your map (or flowchart) as you write code for the paths you designed.

</div> 


<!--
  public class RunestoneTests extends CodeTestHelper
  {
      public RunestoneTests()
      {
          super("Main", input1.replaceAll(" ", "\n")); // For Book
      }

      private static int goal = 5;
      private static String input1 = "n s e w y y y y y y y y y y y y y y";
      private static String input2 = "s e w y n y y y y y y y y y y y y y";
      private static String input3 = "e w y n s y y y y y y y y y y y y y";
      private static String input4 = "w y n s e y y y y y y y y y y y y y";
      private static String input5 = "y n s e w y y y y y y y y y y y y y";
      private String output1, output2, output3, output4, output5;

      @Test
      public void test1()
      {
          String input = input1.replaceAll(" ", "\n");
          String output = getMethodOutputWithInput("main", input);
          output1 = output;

          String[] lines = output.split("\n");

          boolean passed = lines.length >= goal;

          passed =
                  getResults(
                          goal + "+ lines",
                          "" + lines.length + " lines",
                          "Outputs at least " + goal + " lines",
                          passed);
          assertTrue(passed);
      }

      @Test
      public void test2()
      {
          String input = input2.replaceAll(" ", "\n");
          String output = getMethodOutputWithInput("main", input);
          output2 = output;

          input = input3.replaceAll(" ", "\n");
          output = getMethodOutputWithInput("main", input);
          output3 = output;

          input = input4.replaceAll(" ", "\n");
          output = getMethodOutputWithInput("main", input);
          output4 = output;

          input = input5.replaceAll(" ", "\n");
          output = getMethodOutputWithInput("main", input);
          output5 = output;

          if (output1 == null)
          {
              input = input1.replaceAll(" ", "\n");
              output1 = getMethodOutputWithInput("main", input);
          }

          boolean passed =
                  !output1.equals(output2)
                          && !output1.equals(output3)
                          && !output1.equals(output4)
                          && !output1.equals(output5);

          passed =
                  getResults(
                          "true",
                          "" + passed,
                          "Outputs different results for different inputs",
                          passed);
          assertTrue(passed);
      }

      @Test
      public void test3()
      {
          String code = getCode();
          int num = countOccurences(code, "if");
          boolean passed = num >= 4;

          getResults("4", "" + num, "Number of if statements", passed);
          assertTrue(passed);
      }

      @Test
      public void test4()
      {
          String code = getCode();
          int elseif = countOccurences(code, "else if");
          boolean passed = elseif >= 3;

          getResults("" + 3, "" + elseif, "Number of else if statements", passed);
          assertTrue(passed);
      }

      @Test
      public void test5()
      {
          String code = getCode();
          int num = countOccurences(code, "else {");
          boolean passed = num >= 1;

          getResults("1", "" + num, "Number of else statements", passed);
          assertTrue(passed);
      }
  }
  -->

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from []().
{: .fs-2 }
