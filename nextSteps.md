To organize/structure the project, the next steps I want to do will always be added here

❌ = not started yet

🛠️ = currently under construction

✅ = done

🟡 = works for now but improvements planned

### Fifth Week: 24.12. - 30.12.2024

- ❌ add functionality to win/loose the game

  - game over when uncovering a mine -> display message, return to landing screen
  - won when all cells without a mine are uncovered -> display message, return to landing screen
  - `=>` done if winning/loosing a game is working correctly

- ❌ add interaction with the terminal:

  - when starting the game, first some landing screen is displayed ("Welcome to Fair Minesweeper, to start a new game, press S on your keyboard")
  - if S is pressed, generate a new board and display it to the user (here two representation, player board is only Hidden cells here)
  - display new message: "to make a move, press the corresponing keys:
    a number greater/equal to 0 for row and col, an action out of [u(ncover),f(lag),r(emove flag)], q to quit the game (return to landing screen)"
  - "what's the row of your move?"-> player presses key
  - "what's the col of your move?"-> player presses key
  - "what action do you want to do?" -> player presses key
  - display new board after the action if the action was valid
  - display correct error message in case any invalid key was pressed
  - `=>` done if all of the above features are working. Winning/loosing is not in scope here, so the game can only end with the user pressing q

- ✅ add functionality for players:

  - function to validate player's moves (coordinates in board range, trying to uncover an already uncovered cell (Number cell))
  - unflagging a previously flagged cell should be possible
  - terminal interaction currently not in scope, only function that get's a move and returns the new board after the move
  - maintain a new board for players, create it based on size of previously generated solution board
  - recursively uncover adjacent cells when uncovering an empty cell (🟡 floodFill algorithm)
  - `=>` done if a move can be made by calling some function. The move has to be a valid one, otherwise the correct error message get's displayed. In case of uncovering an empty cell, the [floodFill](https://en.wikipedia.org/wiki/Flood_fill) algorithm is used to recursively uncover neighbouring number cells

- 🟡 when printing a board, display a line to seperate between the coordinates and the actual board content
- ✅ remove EmptyCell() and match for Number(0) in printRow instead?
- ✅ add functionality for random placement of mines (create initial board)

  - therefore function(s) to check/maintain the rules (e.g. max 8 mines around each field,...)
  - functionality for players not in scope here, just static board generation
  - mine placement function parametrized by total number of mines
  - idea: input desired number of mines and just place this number of mines at random coordinates on the board (check that coordinates are unique -> no two mines on the same field). Then for each field count the numbers of mines surrounding it (max 8) -> special case: edges (max 3) and borders (max 5). If the number is 0, it's displayed as an empty cell, else the number gets shown
  - `=>` done if a random, correct(correct numbers,...) board can be generated automatically

### Fourth Week: 17.12. - 23.12.2024

- didn't really do anything new

### Third Week: 10.12. - 16.12.2024

- 🛠️ add functionality for random placement of mines (create initial board)

  - therefore function(s) to check/maintain the rules (e.g. max 8 mines around each field,...)
  - functionality for players not in scope here, just static board generation
  - mine placement function parametrized by total number of mines
  - idea: input desired number of mines and just place this number of mines at random coordinates on the board (check that coordinates are unique -> no two mines on the same field). Then for each field count the numbers of mines surrounding it (max 8) -> special case: edges (max 3) and borders (max 5). If the number is 0, it's an EmptyCell, else it's Number cell.
  - check for valid input when generating the board (negative inputs, numMines > size)
  - `=>` done if a random, correct(correct numbers,...) board can be generated automatically

### Second Week: 03.12. - 09.12.2024

- didn't really have time to continue working on the project :(

### First week: 26.11. - 02.12.2024

- ✅ implement representation of the board:

  - data type to store the board in (possible states of a cell: Flag, Bomb, empty, Number and for the player board: hidden or uncovered (-> boolean?))
  - function for updating the state of a field (updateCell)
  - function for printing the board
  - use updateAt function in updateCell
  - `=>` done if an example board can be printed in the terminal correctly and cells can be updated

---

### Rest of the project:

- maintain two boards: one to store the solution in, one for the current state of the player

  - the solution board has no flags, only bombs, numbers and empty fields
  - the player board has no bombs, only flags, numbers and empty fields
  - special case: display bomb/all bombs? when game is lost to the user

- ❌ add functionality for validating player moves

  - make sure fair minesweeper rules + first move rule are maintained
  - again, actual functionality for players (terminal interaction,...) not in scope
  - `=>` done if a given move of the player can be validated by maintainig the rules

- 🛠️ add emojis to represent the board cells

- remove EmptyCell() and match for Number(0) in printRow instead?

- in generateBoard effect to generate player board?

---

- possible property tests:
  - only player boards can have hidden cells
  - a player board can't have a Mine on it (bc then the game should already be lost)
  - as soon as a Cell containing a Mine is revealed, the game is lost
  - mine counting works correctly
  - flood fill works correctly
