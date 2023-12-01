# Number-Guessing-Game
"My first repository on GitHub"
#include <iostream>
#include <random>

using namespace std;

int main() {
    random_device rd;
    mt19937 gen(rd());
    uniform_int_distribution<int> distribution(1, 100);

    int secretNumber = distribution(gen);
    int userGuess;
    int attempts = 0;

    cout << "Welcome to the Number Guessing Game!\n";
    cout << "Try to guess the number between 1 and 100.\n\n";

    do {
        cout << "Enter your guess: ";
        cin >> userGuess;

        attempts++;

        if (userGuess > secretNumber) {
            cout << "Too high! Try again.\n";
        } else if (userGuess < secretNumber) {
            cout << "Too low! Try again.\n";
        } else {
            cout << "\nCongratulations! You guessed the number in " << attempts << " attempts.\n";
        }

    } while (userGuess != secretNumber);

    return 0;
}   
