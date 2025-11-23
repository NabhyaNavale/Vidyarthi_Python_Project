# Vidyarthi_Python_Project

**Cows and Bulls Game**

The Cows and Bulls Game is a classic code-breaking game normally played by two or more players, where one tries to break the code of the other using deduction and reasoning based on the clues given after every guess.

**Objective of the Game**
Each player independently selects a four-figure number, all of whose digits are different.
Players take turns to try and guess each other's secret number.
The aim is to crack the opponent's code based on the feedback after every guess.​

**Gameplay Rules**
The opponent, after a guess, gives the hints:
"Bulls": the number of digits in the guess that are in the proper position within the secret number.
“Cows”: Number of digits in the guess that exist in the secret number, but are in a different position.​

Example: If the secret code is 4271 and a guess is 1234, then the feedback response would be 1 bull ("2" is in the right place) and 2 cows ("4" and "1" are in the number but wrong positions).​ **Winning the Game The first player who guesses all digits in their correct positions, or gets all bulls, wins. The game can be played with numbers, words, or other symbols, provided there are no duplicates allowed.







# CODE
import random
digits = list('123456789') 
random.shuffle(digits)
n="".join(digits[:4])
g_count = 0   
print("Welcome to Bulls and Cows!")
print("A Bull means a correct digit in the correct position.")
print("A Cow means a correct digit in the wrong position.")
print("I've generated a 4-digit number with unique digits. Try to guess it!")
print()
while True:
    bulls = 0
    cows = 0
    g_count += 1
    guess = input(f"Guess #{g_count}: Enter a 4-digit number: ")
    if guess == n:
     break
    n_list= list(n)
    g_list= list(guess)
    for i in range(4):
        if g_list[i] == n_list[i]:
            bulls += 1
    for digit in g_list:
        if digit in n_list:
            cows += 1
    cows -= bulls
    print(f"Result: {bulls} Bull{'s' if bulls != 1 else ''} , "
          f"{cows} Cow{'s' if cows != 1 else ''} ")
print(f" CONGRATS! You have won the game! ")
print(f"It took you only {g_count} guess to win!")
