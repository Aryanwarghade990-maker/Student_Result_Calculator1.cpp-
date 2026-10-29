# Student_Result_Calculator1.cpp-

#include <iostream>
#include <string>
using namespace std;

class Student {
private:
    int rollNumber;
    string name;
    float marks[3]; // marks for 3 subjects
    float total;
    float percentage;
    string result;

public:
    // Function to accept student details
    void acceptDetails() {
        cout << "Enter Roll Number: ";
        cin >> rollNumber;
        cin.ignore(); // clear input buffer
        cout << "Enter Name: ";
        getline(cin, name);
        cout << "Enter marks for 3 subjects: ";
        for (int i = 0; i < 3; i++) {
            cin >> marks[i];
        }
    }

    // Function to calculate result
    void calculateResult() {
        total = 0;
        for (int i = 0; i < 3; i++) {
            total += marks[i];
        }
        percentage = total / 3.0;
        
        if (percentage >= 60) {
            result = "First Class";
        } else if (percentage >= 50) {
            result = "Second Class";
        } else if (percentage >= 40) {
            result = "Pass";
        } else {
            result = "Fail";
        }
    }

    // Function to display student details
    void displayDetails() {
        cout << "\n----- Student Details -----" << endl;
        cout << "Roll Number: " << rollNumber << endl;
        cout << "Name: " << name << endl;
        cout << "Marks: ";
        for (int i = 0; i < 3; i++) {
            cout << marks[i] << " ";
        }
        cout << endl;
        cout << "Total Marks: " << total << endl;
        cout << "Percentage: " << percentage << "%" << endl;
        cout << "Result: " << result << endl;
    }
};

int main() {
    Student s;
    s.acceptDetails();
    s.calculateResult();
    s.displayDetails();
    return 0;
}
