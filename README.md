# ROCK-PAPER-SCISSOR-GAME

import random

def determine_winner(user_choice, computer_choice):
    if user_choice == computer_choice:
        return "It's a tie!"
    elif (user_choice == 'rock' and computer_choice == 'scissors') or \
         (user_choice == 'scissors' and computer_choice == 'paper') or \
         (user_choice == 'paper' and computer_choice == 'rock'):
        return "You win!"
    else:
        return "You lose!"

def print_choices(user_choice, computer_choice):
    print(f"Your choice: {user_choice}")
    print(f"Computer's choice: {computer_choice}")

def play_game():
    user_score = 0
    computer_score = 0
    play = True

    print("Welcome to Rock, Paper, Scissors Game!")
    
    while play:
        user_choice = input("Enter 'rock', 'paper', or 'scissors': ").lower()
        computer_choice = random.choice(['rock', 'paper', 'scissors'])

        if user_choice in ['rock', 'paper', 'scissors']:
            print_choices(user_choice, computer_choice)
            result = determine_winner(user_choice, computer_choice)
            print(result)

            if result == "You win!":
                user_score += 1
            elif result == "You lose!":
                computer_score += 1

            print(f"Your score: {user_score} | Computer's score: {computer_score}")
        else:
            print("Invalid choice! Please enter 'rock', 'paper', or 'scissors'.")

        play_again = input("Do you want to play again? (yes/no): ").lower()
        if play_again != 'yes':
            play = False

    print("Thanks for playing!")

play_game()
