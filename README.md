## Flask Application Design for Incident Investigation Game

## HTML Files

**index.html**
- Homepage that allows the user to create a new game or join an existing game with a code.
- Contains form fields for username and game code (if joining).

**game.html**
- Main game interface where the user can:
  - View the game board, which displays cards and clues for the incident.
  - Perform actions, such as investigating cards, using clues, and proposing solutions.

## Routes

**POST /create_game**
- Creates a new game and redirects the user to the 'game' page.

**POST /join_game**
- Verifies the provided game code and redirects the user to the 'game' page if the code is valid.

**GET /game**
- Handles the initial load of the 'game' page and provides the game data (board, clues, etc.).

**POST /investigate_card**
- Updates the game state when a card is investigated, revealing its contents.

**POST /use_clue**
- Updates the game state when a clue is used, providing additional information about the incident.

**POST /propose_solution**
- Updates the game state when a solution is proposed, checking its correctness and ending the game if it's correct.

**WebSocket /ws**
- WebSocket connection for real-time updates on game state changes (e.g., when a card is investigated or a clue is used).