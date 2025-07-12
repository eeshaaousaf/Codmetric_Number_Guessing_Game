#include <iostream>
#include <cstdlib>
#include <ctime>

using namespace std;

int main() {
    // Seed the random number generator
    srand(time(0));

    // Generate random number between 1 and 100
    int randomNumber = rand() % 100 + 1;
    int userGuess;
    int attempts = 0;

    cout << "=== Number Guessing Game ===" << endl;
    cout << "I have picked a number between 1 and 100." << endl;
    cout << "Can you guess it?" << endl;
    cout << endl;

    // Game loop
    while (true) {
        cout << "Enter your guess: ";
        cin >> userGuess;

        // Input validation
        if (cin.fail()) {
            cout << "Please enter a valid number!" << endl;
            cin.clear();
            cin.ignore(1000, '\n');
            continue;
        }

        attempts++;

        // Check the guess
        if (userGuess == randomNumber) {
            cout << "Congratulations! You guessed it right!" << endl;
            cout << "The number was: " << randomNumber << endl;
            cout << "You took " << attempts << " attempts." << endl;
            break;
        }
        else if (userGuess < randomNumber) {
            cout << "Too low! Try a higher number." << endl;
        }
        else {
            cout << "Too high! Try a lower number." << endl;
        }

        cout << "Attempts so far: " << attempts << endl;
        cout << endl;
    }

    cout << "Thanks for playing!" << endl;
    return 0;
}