# My arcade plan


## Games I chose

- Game 1: Rock-paper-Scissors — difficulty: Easy
- Game 2: Hangman — difficulty: Medium


## Game 1: Rock-paper-Scissors

- Rules, in a few sentences: The player competes against the computer in Rock-Paper-Scissors. The player chooses rock, paper, or scissors, and the computer randomly selects one of the three options. Rock beats scissors, scissors beats paper, and paper beats rock. If both choose the same option, the round is a tie.
- What one turn looks like: One turn is one round. The player enters rock, paper, or scissors. The computer randomly generates its choice. The program displays both choices and announces whether the player won, lost, or tied. Invalid choices display a friendly error message and ask the player to try again.
- How it ends (win, lose, or out of turns): The session ends when either the player or computer wins three rounds. The program announces the final result and returns the player's score to the menu.
- How a score is earned (the formula or rule, and why higher is better): Each round won earns the player one point. Ties and losses earn zero points. The final score is the total number of rounds won. A higher score means the player won more rounds.
- Game settings (the fixed numbers or choices that define the game, such as
  grid size, number of guesses, word length, or question count): The player competes against the computer. There are three possible choices: rock, paper, and scissors. The first player to win three rounds ends the game. Tied rounds do not count toward either player's total wins.

## Game 2: Hangman

- Rules, in a few sentences: The program randomly selects a secret word from a word list. The player must guess the hidden word one letter at a time. Correct guesses reveal the matching letters in the word, while incorrect guesses reduce the number of remaining attempts. The player must reveal the entire word before running out of attempts.
- What one turn looks like: One turn is one letter guess. The player enters a single letter, and the program checks whether that letter is in the secret word. If the guess is correct, the letter is revealed in its correct positions. If the guess is incorrect, one attempt is removed. Previously guessed letters cannot be entered again. Invalid input displays a friendly message and asks the player to try again.
- How it ends (win, lose, or out of turns): The session ends when the player correctly guesses the entire word or uses all six incorrect guesses. The program announces whether the player won or lost and returns the final score to the menu.
- How a score is earned (the formula or rule, and why higher is better): The player starts with six points. Each incorrect guess removes one point. The final score is the number of incorrect guesses remaining. Guessing the word without any incorrect guesses earns six points. A higher score means the player guessed the word with fewer mistakes.
- Game settings (the fixed numbers or choices that define the game, such as
  grid size, number of guesses, word length, or question count): The secret word is randomly selected from a word list committed to the repository. Words contain between four and eight letters. The player is allowed a maximum of six incorrect guesses. Repeated guesses do not count as another incorrect guess.



## Scoreboard fields

Every finished game records the player's name and final score. I will keep the default scoreboard layout, where the game's module name identifies the game. Each game's records are stored separately under its module name.
Example JSON structure:

{
    "rock_paper_scissors": [
        {"player": "Sam", "score": 3},
        {"player": "Ada", "score": 2}
    ],
    "hangman": [
        {"player": "Sam", "score": 5},
        {"player": "Ada", "score": 3}
    ]
}

## Pure functions and testing

Each game will use pure functions to handle its game rules and calculations. Rock-Paper-Scissors will have functions to determine the winner of each round and calculate the score. Hangman will have functions to check guessed letters, determine whether the word has been completed, and calculate the remaining guesses. These functions will be tested using pytest.