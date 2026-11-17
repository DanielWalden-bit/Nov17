#include <iostream>
using namespace std;

int main() {
    string word = "cat";
    string guess = "___";
    char letter;
    int tries = 5;

    while (tries > 0 && guess != word) {
        cout << "\nWord: " << guess << endl;
        cout << "Guess a letter: ";
        cin >> letter;

        bool right = false;

        for (int i = 0; i < word.length(); i++) {
            if (word[i] == letter) {
                guess[i] = letter;
                right = true;
            }
        }

        if (!right) {
            tries--;
            cout << "Wrong! Tries left: " << tries << endl;
        }
    }

    if (guess == word)
        cout << "You win!" << endl;
    else
        cout << "You lose! The word was " << word << endl;

    return 0;
}
