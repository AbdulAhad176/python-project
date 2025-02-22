import random

lowest_num = 1
highest_num = 100
random_num = random.randint(lowest_num, highest_num)
guesses = 0
is_running = True

print("Python Number Guessing Game")
print(f'Guess a number between {lowest_num} and {highest_num}')

while is_running:
    user_guess = input('Enter your guess: ')

    if user_guess.isdigit():
        user_guess = int(user_guess)
        guesses += 1

        if user_guess < lowest_num or user_guess > highest_num:
            print("That number is out of range.")
            print(f'Please guess a number between {lowest_num} and {highest_num}.')
        elif user_guess < random_num:
            print("That number is too low.")
        elif user_guess > random_num:
            print("That number is too high.")
        else:
            print(f"CORRECT! The answer was {random_num}.")
            print(f"You got it in {guesses} guesses.")
            is_running = False
    else:
        print("Invalid guess.")
        print(f'Please enter a number between {lowest_num} and {highest_num}.')
