# CodSoft-Project-Rock-Paper-Scissors-Game


# Task 4: Rock-Paper-Scissors Game
This project is a Python-based implementation of the classic Rock-Paper-Scissors Game. It allows the user to play multiple rounds against the computer and keeps track of the scores. The game includes features like random computer choices, user input validation, and a user-friendly interface.


---

# Features

1️⃣ User Input:

The user is prompted to enter their choice: rock, paper, or scissors.

Users can also type exit to quit the game.


2️⃣ Computer Selection:

The computer randomly chooses between rock, paper, or scissors using Python’s random.choice() function.


3️⃣ Game Logic:

The game determines the winner based on the following rules:

Rock beats Scissors

Scissors beat Paper

Paper beats Rock



4️⃣ Display Result:

After every round, the program:

Displays the user’s and computer’s choices.

Announces the winner of the round.



5️⃣ Score Tracking:

The game keeps track of both the user's and the computer's scores across multiple rounds.


6️⃣ Play Again:

After each round, the game asks if the user wants to continue. The game runs until the user types exit.



---

Code Explanation

import random

The random module is imported to allow the computer to make a random choice between rock, paper, and scissors.


Functions

1. get_computer_choice():

Generates a random choice (rock, paper, or scissors) for the computer.


def get_computer_choice():
    choices = ["rock", "paper", "scissors"]
    return random.choice(choices)


2. determine_winner(user_choice, computer_choice):

Compares the user’s choice and the computer’s choice to determine the winner.

Returns the result: "You win!", "Computer wins!", or "It's a tie!".


def determine_winner(user_choice, computer_choice):
    if user_choice == computer_choice:
        return "It's a tie!"
    elif (user_choice == "rock" and computer_choice == "scissors") or \
         (user_choice == "scissors" and computer_choice == "paper") or \
         (user_choice == "paper" and computer_choice == "rock"):
        return "You win!"
    else:
        return "Computer wins!"


3. play_game():

This is the main function that:

Prompts the user for their choice.

Calls other functions to get the computer’s choice and determine the winner.

Keeps track of scores.

Displays the final result when the user exits.



def play_game():
    print("Welcome to Rock-Paper-Scissors Game!")
    user_score = 0
    computer_score = 0

    while True:
        print("\nChoices: Rock, Paper, Scissors")
        user_choice = input("Enter your choice (or 'exit' to quit): ").lower()

        if user_choice == "exit":
            print("\nFinal Score:")
            print(f"You: {user_score}, Computer: {computer_score}")
            print("Thank you for playing!")
            break

        if user_choice not in ["rock", "paper", "scissors"]:
            print("Invalid choice. Please try again.")
            continue

        computer_choice = get_computer_choice()
        print(f"\nYou chose: {user_choice}")
        print(f"Computer chose: {computer_choice}")

        result = determine_winner(user_choice, computer_choice)
        print(result)

        # Update scores
        if result == "You win!":
            user_score += 1
        elif result == "Computer wins!":
            computer_score += 1

        print(f"Score: You - {user_score}, Computer - {computer_score}")


4. if _name_ == "_main_"::

Ensures the game starts by calling the play_game() function.


if _name_ == "_main_":
    play_game()




---

How It Works

1. When the program starts, it displays a welcome message.


2. The user is prompted to enter their choice (rock, paper, or scissors).


3. The computer generates a random choice.


4. The game determines the winner based on the rules.


5. The scores are updated and displayed after each round.


6. The game continues until the user types exit, at which point the final scores are displayed.




---

Example Output

Round 1:

Welcome to Rock-Paper-Scissors Game!

Choices: Rock, Paper, Scissors
Enter your choice (or 'exit' to quit): rock

You chose: rock
Computer chose: scissors
You win!
Score: You - 1, Computer - 0

Round 2:

Choices: Rock, Paper, Scissors
Enter your choice (or 'exit' to quit): paper

You chose: paper
Computer chose: scissors
Computer wins!
Score: You - 1, Computer - 1

Exit:

Choices: Rock, Paper, Scissors
Enter your choice (or 'exit' to quit): exit

Final Score:
You: 1, Computer: 1
Thank you for playing!


---

Key Learnings

Python random module for generating random choices.

Control flow using if-elif-else statements for game logic.

Input validation to handle invalid user inputs.

Looping (while True) for continuous gameplay.

Displaying real-time scores.



---

Suggestions for Improvement

Add more options (like "Lizard" and "Spock") to make the game more interesting.

Create a graphical user interface (GUI) using tkinter.

Add animations or sounds for a more interactive experience.



---

Aap is explanation ko apne project ke documentation ke liye use kar sakte hain. Agar aur help chahiye, toh bataiye!
