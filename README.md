# Noughts-and-Crosses-Tic-Tac-Toe-Game-Python-Project
Developed a command-line-based Noughts and Crosses game in Python that allows two players to play the classic game. The game includes player input validation, win condition checks, and interactive turn-based gameplay.

**Key Features:**

Interactive command-line interface for player moves.
- Checks for valid moves and prevents overwriting existing moves.
- Detects winning conditions for both "X" and "O."
- Implements a turn-based system for two players.
- Utilizes Python data structures for game state management.

**Technologies and Tools:**
Python


def printBoard(xstate, zstate):
    zero = 'X' if xstate[0] else ('O' if zstate[0] else 0)
    one = 'X' if xstate[1] else ('O' if zstate[1] else 1)
    two = 'X' if xstate[2] else ('O' if zstate[2] else 2)
    three = 'X' if xstate[3] else ('O' if zstate[3] else 3)
    four = 'X' if xstate[4] else ('O' if zstate[4] else 4)
    five = 'X' if xstate[5] else ('O' if zstate[5] else 5)
    six = 'X' if xstate[6] else ('O' if zstate[6] else 6)
    seven = 'X' if xstate[7] else ('O' if zstate[7] else 7)
    eight = 'X' if xstate[8] else ('O' if zstate[8] else 8)
    
    print(f"{zero} | {one} | {two}")
    print("--| --| --")
    print(f"{three} | {four} | {five}")
    print("--| --| --")
    print(f"{six} | {seven} | {eight}")

def checkwin(xstate, zstate):
    wins = [[0, 1, 2], [3, 4, 5], [6, 7, 8], [0, 3, 6], [1, 4, 7], [2, 5, 8], [0, 4, 8], [2, 4, 6]]
    
    for win in wins:
        if xstate[win[0]] + xstate[win[1]] + xstate[win[2]] == 3:
            print("X won the match")
            return 1
        if zstate[win[0]] + zstate[win[1]] + zstate[win[2]] == 3:
            print("O won the match")
            return 0
    return -1

if __name__ == "__main__":
    xstate = [0, 0, 0, 0, 0, 0, 0, 0, 0]
    zstate = [0, 0, 0, 0, 0, 0, 0, 0, 0]
    turn = 1  # 1 for X and 0 for O
    print("Noughts and Crosses")
    
    while True:
        printBoard(xstate, zstate)
        
        if turn == 1:
            print("X's chance")
            value = int(input("Please enter a Value: "))
            if xstate[value] == 0:
                xstate[value] = 1
            else:
                print("Invalid move. Try again.")
        else:
            print("O's chance")
            value = int(input("Please enter a Value: "))
            if zstate[value] == 0:
                zstate[value] = 1
            else:
                print("Invalid move. Try again.")
        
        cwin = checkwin(xstate, zstate)
        if cwin != -1:
            print("Match Over")
            break
        turn = 1 - turn



**Responsibilities**:

- Game logic and functionality design.
- Code implementation, including the game board, player moves, and win condition checks.
- User input validation and error handling.
- Testing and debugging to ensure game accuracy.




