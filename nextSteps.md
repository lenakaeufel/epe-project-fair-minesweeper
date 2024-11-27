To organize/structure the project, the next steps I want to do will always be added here

❌ = not started yet

🛠️ = currently under construction

✅ = done

🟡 = works for now but improvements planned

### First week: 26.11. - 03.12.2024

- 🛠️ implement representation of the board:

  - data type to store the board in
  - function for setting the state of a field
  - function for printing the board
  - `=>` done if an example board can be printed in the terminal correctly

- ❌ add functionality for random placement of mines (create initial board)

  - therefore function(s) to check/maintain the rules (e.g. max 8 mines around each field,...)
  - functionality for players not in scope here, just static board generation
  - mine placement function parametrized by total number of mines
  - `=>` done if a random, correct(correct numbers,...) board can be generated automatically

- ❌ add functionality for validating player moves
  - make sure fair minesweeper rules + first move rule are maintained
  - again, actual functionality for players (terminal interaction,...) not in scope
  - `=>` done if a given move of the player can be validated by maintainig the rules
