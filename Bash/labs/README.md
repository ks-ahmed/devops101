# Scenario:
### Create a Bash script where the user has to guess a secret number. 

**The script will:**

  1. Set a secret number (eg. 7) 
  2. Keep asking the user to guess the number until they get it right. 
  3. Give feedback if the guess is too high or too low.

---

### Live demo:

https://github.com/user-attachments/assets/fe51b168-54b0-43a5-9701-e36e3f0fca70

---
### Overview:

`#!/bin/bash` : called a shebang - used at the top of a script file to tell the os which interpreter to use to run the script.

`secret_number= 7` : This line sets the secret number the player is trying to guess.

`while true; do`   : while true creates an infinite loop, meaning the game keeps running until we manually stop it (which we do          using               break when the guess is correct).

`echo "Guess the secret-number between 1-10:"`  : This shows a message to the user, asking for their guess. \
`read number`  : This line reads the user’s input and saves it to the variable number.

`if [ $number -eq $secret_number ]; then` \
`echo "Congrats, you've guessed the correct number!"` \
`break` 
        
^ : If the guessed number is equal to the secret number, the program congratulates the user and breaks the loop to stop the                 game.

`elif [ $number -gt $secret_number ]; then` \
`echo "Number too high, please try again!"` \
        
^ : If the guessed number is greater than the secret number, the program says it's too high and lets the user try again.
        
`else` \
`echo "Number too low, please try again!"` \
`fi` 
      
^ : If the guess is neither equal nor greater, it must be lower, so the program says it’s too low. `fi` ends the if block.

`done` :  This marks the end of the loop block. If the user hasn't guessed correctly, the loop starts over and asks again.

---

### Final Summary in Simple Terms:

  - This script is a guessing game. The computer secretly picks the number 7, and the player keeps guessing until they get it right.
  - Each time they guess, the computer tells them if their guess is too high, too low, or correct.
  - The game stops when the correct number is guessed.
