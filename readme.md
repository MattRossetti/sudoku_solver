# Sudoku Solver

## Overview
This project contains python code to solve sudokus.

## How To Solve
1. Open solver.ipynb
2. Run Cells 0-12, this initiates the solving algorithms
3. Run Cell 13, change the text in reset_board to any of the boards in boards.py. You can also add your own board to the boards.py file, and update the reset_board function to include this board)
4. Run Cell 14 to verify the starting board is correct
5. run Cell 15 to solve the sudoku,  if the board is solved, the solved board will be printed.
6. Examine step_1_writing_guarenteed_values.txt and step_2_solving_recusively.txt files to follow the algorithm step by step. Note, step_2_solving_recusively.txt may be empty. It is not always needed as it the second step in the algorithm.

## How it works
1. Python first ingests the sudoku board as list of lists, the display_game_board function turns prints the board to look like a regular sudoku board.
2. A two part solving algorithm is implemented to solve the board
3. The board, and information for the next step in the solving algorithm is writen to either step_1_writing_guarenteed_values.txt or step_2_solving_recusively.txt depending on which step

## How the solving algorithm works
The solving algorithm is broken down into 2 steps:

### Step 1, Writing Guarenteed Values
The algorithm loops through each square and checks the row, column, and its surrounding square to see which values of 1-9 the square cannot be. This is used to generate a list of possibilities for the square. if the list of possibilities has a length of 1, this means that there is only one possibility for that square and the number is then written into that square on the board. After looping through each square on the board and applying this logic, if any square was updated the algorithm will loop through each square again, this time with the newly added numbers, if no squares are updated it moves on to Step 2. This algorithm can be followed step by step in the step_1_writing_guarenteed_values.txt file.


### Step 2, Recursive solving
In step 2 the algorithm uses recursion to find a solution to the missing squares. The algorithm starts at the first square on the grid, generates a list of possibilites, and picks the lowest number in this list, this guess is then added to a list of values already tried by the algorithm. The new board is then passed into the same alrogithm recursively and it does the same for logic for the next square. If the algorithm gets to a point where the board is not solved and there is no possibilities for the current square. It moves back to previously updated square and tries the next possible value for that square. This progress can be followed step by step in the step_2_solving_recusively.txt file
