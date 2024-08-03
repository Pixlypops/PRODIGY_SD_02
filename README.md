# PRODIGY_SD_02

# Guessing Game README

## Introduction

Welcome to the Guessing Game! This is a simple console-based game where you try to guess a randomly generated number within a specified range. You have a limited number of chances to guess the correct number, and you receive hints along the way to help you make the right guess.

## Rules of the Game

1. **Number of Chances**: You have 5 chances to guess the number.
2. **Range**: The number to guess is between 1 and 439.
3. **Objective**: Guess the number in the fewest possible attempts.
4. **Hints**: After each guess, you will receive a hint indicating whether your guess is too high or too low.
5. **Starting Points**: You start the game with 100 points.
6. **Points Deduction**: Each incorrect guess will cost you 20 points.
7. **Winning Points**: If you guess the number correctly, you will receive 100 points.
8. **Losing**: If you use all your chances without guessing the number, you will lose the game.
9. **Winning**: If you guess the number correctly within the given chances, you win the game.
10. **Good Luck**: Have fun and good luck!

## How to Play

1. **Start the Game**: Run the program to start the game.
2. **Input Your Guess**: Enter a number between 1 and 439 when prompted.
3. **Receive Hints**: After each guess, you will be told if your guess is too high or too low.
4. **Win or Lose**: Keep guessing until you either guess the correct number or run out of chances.

## Code Breakdown

### Header Files
```cpp
#include <iostream>
#include <cstdlib>
#include <ctime>
using namespace std;
```
- `#include <iostream>`: Allows for input and output operations.
- `#include <cstdlib>`: Includes functions for random number generation.
- `#include <ctime>`: Includes functions for time manipulation.

### Main Function
```cpp
int main() {
  // Introduction and rules display
  cout << "======================================" << endl;
  cout << "== Welcome to the Guessing Game ==" << endl;
  cout << "======================================" << endl;
  // Display game rules
  cout << "|RULES OF THE GAME|" << endl;
  cout << " ----------------- " << endl;
  // Rules as described in the game
  // Random number generation setup
  srand(time(0));
  int randomNumber = rand() % 498 + 1;
  int playerGuess;
  int count = 0;
  int points = 100;
  int maxCount = 5;
  
  // Game loop
  while (count < maxCount) {
    cout << "Please Enter a Number Between 1 and 439: ";
    cin >> playerGuess;
    // Input validation
    if (playerGuess < 1 || playerGuess > 439) {
      cout << "Invalid Input. Please Enter a Number Between 1 and 439: ";
      continue;
    }
    // Provide hints and update points and count
    if (playerGuess > randomNumber) {
      cout << "\n\nYour guess is too high. Please try again.\n";
      count++;
      points -= 20;
    } else if (playerGuess < randomNumber) {
      cout << "\n\nYour guess is too low. Please try again.\n";
      count++;
      points -= 20;
    } else {
      // Winning condition
      count++;
      cout << "\n\n\nCongratulations! You have guessed the number in " << count << " tries.\n";
      cout << "You have won the game!\n";
      cout << "You won with " << points << " ppoints left\n";
      return 0;
    }
  }
  
  // Losing condition
  if (count >= maxCount) {
    cout << "Sorry, you have used all your chances. You have lost the game.\n";
    return 0;
  }
}
```

### Game Flow
1. **Introduction and Rules Display**: The game starts with a welcome message and displays the rules.
2. **Random Number Generation**: A random number between 1 and 439 is generated.
3. **Game Loop**: The player is prompted to guess the number. The loop continues until the player guesses correctly or exhausts the allowed number of guesses.
4. **Hints and Points Update**: After each guess, the player is given a hint and the points are updated accordingly.
5. **Win or Lose**: The game ends with a win or lose message based on the player's guesses.

## Compilation and Execution

1. **Compilation**: Compile the code using a C++ compiler.
   ```sh
   g++ -o guessing_game guessing_game.cpp
   ```
2. **Execution**: Run the compiled program.
   ```sh
   ./guessing_game
   ```

Enjoy playing the Guessing Game!
