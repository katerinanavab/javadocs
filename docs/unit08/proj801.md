---
layout: project
title: "💻 PROJECT #8.1"
projectname: "Grid Game"
parent: "8️⃣ 2D Arrays"
nav_order: 5
---

### Overview & Setup

🎲🃏🧩 You will design and implement a **grid-based game** in Java using **2D arrays**. Your game should use a **10×10 grid** (_or another size of your choice_) `object` to store and update game state. You can model classic games (_e.g., Battleship, Minesweeper, Tic-Tac-Toe_) or create your own!

This project will strengthen your understanding of:
- **Declaring & initializing** 2D arrays
- **Accessing & modifying** elements in a 2D array
- **Iterating** through 2D arrays using **nested loops**

#### 🧠 Brainstorming Ideas
Not sure where to start? Look into these examples:
- **Classic Grid Games:** Tic-Tac-Toe, Battleship, Minesweeper, Connect Four, Checkers
- **Dungeon Crawler:** A player moves through a grid avoiding traps and collecting items.
- **Snake Game:** A randomly-placed snake grows as it eats food, avoiding walls and itself.

#### 💡 Planning Prompts
In your `README.md` file, answer the following questions about your chosen game:
1. What is the _structure_ of the grid? What _data type_ would be appropriate for the individual **grid cells**? (`char` for single symbols, `String` for words, `int` or `double` for numerical values)
  > Consider using **two** same-size 2D arrays if you need to "hide" the full board from the player, like in Battleship.
2. How does a _round of gameplay_ look? What _actions_ can the player take?
3. How does _scorekeeping_ look? What is the criteria for a win?

<div class="setup" markdown="block">

1. Go to the `CS2 Project 8.1` assignment on **Blackbaud** and follow the provided **GitHub Classroom** link.
  > 📁 Clicking the link generates a **private repository** for your project with the appropriate starter code. Note that **projects** are stored within the [BWL-CS Organization](https://github.com/BWL-CS), so you _cannot_ access it from the "Your Repositories" page!
2. Open the repository in a **Codespace** whenever you spend time working on the program, in class or at home. 
  > ⚠️ Always remember to `commit changes` after every coding session!
3. When your project is complete, submit the link to your **repository page** (*not the Codespace!*) in the `CS2 Project 8.1` assignment on Blackbaud.

</div>

---

### Project Requirements
Your program should:
- ✅ Use a **2D array** to store the game board.  
- ✅ Implement **at least one method** that modifies the grid.  
- ✅ Allow **player input** to update the grid (_e.g., move a character, place a symbol_).  
- ✅ Display the **updated grid** after each move.  
- ✅ Implement **win/lose conditions**.  

#### Bonus Features (Optional)
- 🌟 Use **randomized elements** (e.g., randomly place enemies or obstacles).  
- 🌟 Implement **multiple players or an AI opponent**.  
- 🌟 Add **a graphical user interface (GUI)** using Java Swing.

---

### Instructions & Guidelines

#### 1. Set Up Your Grid

<div class="task" markdown="block">
  
Open a new file called `GridGame.java` and copy in the starter code below to define a `GridGame` class.

- Creates a **2D array** (`char[][] grid`) to store the game board.
- Initializes it with a **default value** (e.g., `'-'` for an empty cell).
- Includes a method to **print the grid** so players can see it.
  
```java
public class GridGame {
    private static final int SIZE = 3;  // Adjust for different grid sizes
    private char[][] grid;

    public GridGame() {
        grid = new char[SIZE][SIZE]; 
        initializeGrid();
    }

    public void initializeGrid() {
        for (int r = 0; r < SIZE; r++) {
            for (int c = 0; c < SIZE; c++) {
                grid[r][c] = '-';  // Use '-' to indicate an empty space
            }
        }
    }

    public void displayGrid() {
        for (int r = 0; r < SIZE; r++) {
            for (int c = 0; c < SIZE; c++) {
                System.out.print(grid[r][c] + " ");
            }
            System.out.println();
        }
    }
}
```
> 🧪 _TEST_ the code above in your `Main.java` file's `main` method with a call to the **constructor** to create a `GridGame` object, followed by a call to the `displayGrid()` method.

</div>

#### 2. Implement Player Moves

<div class="task" markdown="block">

- Ask the player for a **row and column number**.
  > ⚠️ Don't forget to `import java.util.Scanner` in your `Main.java` file.
- Place their symbol (`'X'`, `'O'`, or other) at the given position.
- Prevent **invalid moves** (e.g., out-of-bounds positions or occupied spaces).

_EXAMPLE:_ Use **if statements** to check if a move is legal before updating the grid.

```java
// 3x3 Tic-Tac-Toe Example
public void playerMove(int row, int col) {
  if (row >= 0 && row < SIZE && col >= 0 && col < SIZE && grid[row][col] == '-') {
    grid[row][col] = 'X';
  }
  else {
    System.out.println("Invalid move. Try again.");
  }
}
```
> Write any gameplay **method definitions** like the one above in the `GridGame.java` class.

Handle the **gameplay loop** in the `Main.java` class' `main` method:
```java
while (true) {
  game.displayGrid();
  System.out.print("Enter row and column (0-2) to place your mark (X): ");
  int row = scanner.nextInt();
  int col = scanner.nextInt();
  game.playerMove(row, col);
}
```

</div>

#### 3. Implement Win Conditions

<div class="task" markdown="block">

- Decide on your game's **rules and objectives**.
- Implement **winning conditions** if needed (_e.g., three in a row for Tic-Tac-Toe_).
- Consider adding **random events** (_e.g., hidden traps or treasure_).

*EXAMPLE:* For Tic-Tac-Toe, check **rows, columns, and diagonals** for three matching symbols.
```java
// 3x3 Tic-Tac-Toe example
public boolean checkWin(char symbol) {
    // Check rows and columns
    for (int i = 0; i < SIZE; i++) {
        if ((grid[i][0] == symbol && grid[i][1] == symbol && grid[i][2] == symbol) || 
            (grid[0][i] == symbol && grid[1][i] == symbol && grid[2][i] == symbol)) {
            return true;
        }
    }
    // Check diagonals
    if ((grid[0][0] == symbol && grid[1][1] == symbol && grid[2][2] == symbol) ||
        (grid[0][2] == symbol && grid[1][1] == symbol && grid[2][0] == symbol)) {
        return true;
    }
    return false; // No win found
}
```

</div>

#### 4. Enhance the Game

<div class="task" markdown="block">

- Use **emojis or ASCII art** to make the grid look better in the console.
- Add a **score counter** or a **turn limit**.
- Make the game **multi-round** or **multiplayer**.
  > *HINT:* Use **loops and conditionals** to track rounds and game progress.
- Make an AI that plays **random moves** in an empty spot like in the example below.

```java
// 3x3 Tic-Tac-Toe AI Move
public void aiMove() {
    int row = (int) (Math.random() * SIZE);
    int col = (int) (Math.random() * SIZE);
    
    // Keep finding a random empty spot
    while (grid[row][col] != '-') {
        row = (int) (Math.random() * SIZE);
        col = (int) (Math.random() * SIZE);
    }

    grid[row][col] = 'O';  // AI places an 'O'
}
```

</div>

### Extensions
- 🎲 **Want randomness?** Randomize enemy placement or obstacles using `Math.random()`.
- 🎨 **Want graphics?** Try using Java Swing GUI for a visual game.
  > See my `Java Swing` demo: [GitHub Swing GUI](https://github.com/katerinanavab/JavaGUI-Demo). 
- 🤖 **Want a better AI?** Implement a simple _minimax_ algorithm for Tic-Tac-Toe.
  > Refer to [Minimax Algorithm in Game Theory](https://www.geeksforgeeks.org/minimax-algorithm-in-game-theory-set-1-introduction/).


