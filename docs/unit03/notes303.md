---
layout: notes
title: "📓3.3: If-Else Statements" 
parent: "3️⃣ Conditionals"
nav_order: 3
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 3.3](https://runestone.academy/ns/books/published/csawesome/Unit3-If-Statements/topic-3-3-if-else.html?mode=browsing) 

<div class="setup" markdown="block">

📝 Take notes in a **Codespace** during class, coding along with the instructor.

1. Go to GitHub and click on your picture in the _TOP RIGHT_ corner
2. Select `Your repositories`
3. Open `CS2-Unit-3-Notes`
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` (unless you already have one listed there), wait for the environment to load, _then you're ready to code_!

</div>


## Two-way Selection: if-else Statements

What if you want to _pick between two possibilities_?  If you are trying to decide between a couple of things to do, you might flip a coin and do one thing if it lands as heads and another if it is tails.  In programming, you can use the `if` keyword followed by a statement or block of statements, and then the `else` keyword also followed by a statement or block of statements.

<div class="imp" markdown="block">
  
```java
// A block if/else statement
if (boolean expression) {
  statement1;
  statement2;
}
else {
  statement3;
  statement4;
}
```
</div>

The following flowchart demonstrates that if the **condition** (the _boolean expression_) is `true`, one block of statements is executed, but if the condition is `false`, a different block of statements inside the else clause is executed:

![image](Figures/Condition-two.png)

{:.highlight}
The `else` block will only execute if the **condition** in the `if`-statement block evaluates to `false`!

### Relational Operators in If-Else Statements

If/else statements can also be used with **relational operators** and numbers like below. If your code has an if/else statement, you should test it with 2 test-cases to make sure that both blocks of the code work.

<div class="task" markdown="block">

1. Test the following code to see what it prints out when the variable `age` is set to the value 16:
```java
int age = 16;
if (age >= 16) {
  System.out.println("You can get a driver's license in most states!");
}
else {
  System.out.println( "Sorry, you need to be older to get a driver's license.");
}
```
2. Change the variable `age`'s value to 15 or younger, and then run it again to see the result of the print statement in the else part.
3. Can you modify the if-statement to indicate that you can get a license at age 17 instead of 16? _This is true for the state of New York._
> Again, try 2 test cases for the value of `age` to test your code to see the results of both print statements.

</div>

### Nested Ifs and "Dangling Else"

If statements can be **nested** inside other if statements. This is like asking a "follow-up question" after asking passing the first one.

{:.warning}
Sometimes with _nested ifs_ we find a **"dangling else"** that could potentially belong to either `if` statement. The rule is that the `else` clause will always be a part of the **closest unmatched** `if` statement in the same block of code, regardless of indentation.

```java
    // Nested if with dangling else
    if (boolean expression)
       if (boolean expression)
          Do statement;
       else  // belongs to closest if
          Do other statement;
```

#### 💻 In-Class Activity: 20 Questions
{:.no_toc}

Have you ever played **20 Questions**? 20 Questions is a game where one person thinks of an object, and the other players ask up to 20 questions to guess what it is.

There is great online version called [Akinator](https://en.akinator.com/) that guesses whether you are thinking of a real or fictional character by asking you questions. Akinator is a simple _Artificial Intelligence_ algorithm that uses a **decision tree** of yes or no questions to pinpoint the answer.
> Although Akinator needs a very large decision tree, we can create a guessing game for just animals using a much smaller number of `if`-statements.


<div class="task" markdown="block">

1. Go to <a href="https://runestone.academy/ns/books/published/csawesome/Unit3-If-Statements/topic-3-3-if-else.html?mode=browsing"><button type="button" name="button" class="btn">CSAwesome Topic 3.3</button></a> 
2. Make sure you **SIGN IN**!
3. Complete the **Programming Challenge: 20 Questions** activity in pairs.

</div>

---

## ⭐️ Summary

- If statements can be followed by an associated **else** block to form a 2-way branch:
```java
// A block if/else statement
if (boolean expression) {
  statement1;
  statement2;
}
else {
  statement3;
  statement4;
}
```

- A **two way selection** (if/else) is written when there are two sets of statements: one to be executed when the Boolean condition is `true`, and another set for when the Boolean condition is `false`.
  - The body of the "if" statement is executed when the Boolean condition is `true`, and the body of the "else" is executed when the Boolean condition is `false`.
  - Use 2 test-cases to find errors or validate results to try both branches of an if/else statement.

- The else statement attaches to the closest unmatched if statement in the same block of statements.


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
