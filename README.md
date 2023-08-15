# Password-Manager-
c++ project
#include <iostream>
#include <unordered_map>

using namespace std;

int main() {
    unordered_map<string, string> passwordMap;

    while (true) {
        cout << "1. Add a password\n";
        cout << "2. Retrieve a password\n";
        cout << "3. Quit\n";
        cout << "Enter your choice: ";
        int choice;
        cin >> choice;

        if (choice == 1) {
            cout << "Enter the website: ";
            string website;
            cin >> website;
            cout << "Enter the password: ";
            string password;
            cin >> password;
            passwordMap[website] = password;
            cout << "Password added successfully!\n";
        } else if (choice == 2) {
            cout << "Enter the website: ";
            string website;
            cin >> website;
            if (passwordMap.find(website) != passwordMap.end()) {
                cout << "Password for " << website << ": " << passwordMap[website] << endl;
            } else {
                cout << "No password found for " << website << endl;
            }
        } else if (choice == 3) {
            break;
        } else {
            cout << "Invalid choice. Please try again.\n";
        }
    }

    return 0;
}
