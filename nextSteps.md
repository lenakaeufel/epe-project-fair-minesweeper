To organize/structure the project, the next steps I want to do will always be added here

❌ = not started yet

🛠️ = currently under construction

✅ = done

🟡 = works for now but improvements planned

### Third Week: 10.12. - 16.12.2024

- 🛠️ add functionality for random placement of mines (create initial board)

  - therefore function(s) to check/maintain the rules (e.g. max 8 mines around each field,...)
  - functionality for players not in scope here, just static board generation
  - mine placement function parametrized by total number of mines
  - idea: input desired number of mines and just place this number of mines at random coordinates on the board (check that coordinates are unique -> no two mines on the same field). Then for each field count the numbers of mines surrounding it (max 8) -> special case: edges (max 3) and boarders (max 5). If the number is 0, it's an EmptyCell, else its Number cell.
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

---

- possible property tests:
  - only player boards can have hidden cells
  - a player board can't have a Mine on it (bc then the game should already be lost)
  - as soon as a Cell containing a Mine is revealed, the game is lost
