# README - Shortest Word Ladder Program

## Overview

This program finds the shortest possible word ladder between two words of a specified length. A "word ladder" is a sequence of words where each word differs from the next by exactly one letter. The program uses a dictionary file as input and builds a word ladder starting from a user-specified word, ending with another word of the same length from the dictionary.

## Key Features
- **Word Ladder Algorithm**: Finds the shortest sequence of words that transform the start word into the final word.
- **Interactive Input**: The user is prompted to enter a dictionary file, word length, and start and end words.
- **File Handling**: The program reads the dictionary from a file and validates that the words meet the desired length.
- **Memory Management**: The program dynamically allocates memory for storing words and word ladders, ensuring proper deallocation when done.

## How It Works
1. **Input**:
   - User specifies a word length and provides a dictionary file containing words.
   - The program verifies that the dictionary contains enough words of the specified length.
   - The user inputs the start and final words from the dictionary for the word ladder.

2. **Processing**:
   - The program builds an array of words from the dictionary file that match the specified word length.
   - It then uses a breadth-first search algorithm to find the shortest word ladder from the start word to the final word, ensuring that each word in the ladder differs by only one letter.
   
3. **Output**:
   - If a ladder is found, the program prints the shortest word ladder and its height (i.e., the number of steps in the ladder).
   - If no ladder is possible, it informs the user.

## Program Files
- `shortest_word_ladder.c`: The main source code file containing the implementation of the word ladder algorithm and helper functions.
  
## Functions
- **countWordsOfLength**: Counts words of a specific length in the dictionary file.
- **buildWordArray**: Fills an array with words of the correct length from the file.
- **findWord**: Uses binary search to locate a word in the sorted word array.
- **freeWords**: Frees memory allocated for the word array.
- **insertWordAtFront**: Inserts a word at the front of a word ladder.
- **getLadderHeight**: Returns the number of words in a word ladder.
- **copyLadder**: Creates a copy of a word ladder.
- **freeLadder**: Frees the memory for a word ladder.
- **insertLadderAtBack**: Adds a word ladder to the end of a ladder list.
- **popLadderFromFront**: Removes and returns the first word ladder from the list.
- **freeLadderList**: Frees all memory allocated for the list of ladders.
- **findShortestWordLadder**: Main algorithm to find the shortest word ladder.
- **setWord**: Allows user to input and validate a word from the dictionary.
- **printLadder**: Displays a single word ladder.
- **printList**: Displays the full list of ladders.

## Usage Instructions
1. Compile the program using a C compiler (e.g., `gcc`):
   ```bash
   gcc shortest_word_ladder.c -o word_ladder
   ```
2. Run the program:
   ```bash
   ./word_ladder
   ```
3. Follow the on-screen prompts:
   - Enter the desired word length.
   - Provide the dictionary file.
   - Input the start and end words for the word ladder.

## Example
1. **Input**:
   ```
   Enter the word size for the ladder: 5
   Enter filename for dictionary: dictionary.txt
   Setting the start 5-letter word... (e.g., "apple")
   Setting the final 5-letter word... (e.g., "grape")
   ```
2. **Output**:
   ```
   Shortest Word Ladder found!
       apple
       ample
       grape
   Word Ladder height = 3
   ```

## Error Handling
- If the dictionary file is not found, or if there are insufficient words of the specified length, the program will terminate with an error message.
- If the user fails to provide a valid word after multiple attempts, the program selects a random word from the dictionary.

## Memory Management
- The program ensures that all dynamically allocated memory (for words, ladders, and lists) is properly freed before exiting to avoid memory leaks.

## Author
Conor McJannett
