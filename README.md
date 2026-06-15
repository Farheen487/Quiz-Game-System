# Quiz-Game-System
A Quiz Game System developed in C++ using Object Oriented Programming concepts.

Quiz Game System is a console-based application developed in C++ using Object-Oriented Programming (OOP) concepts. The project allows users to participate in a multiple-choice quiz, submit answers, receive instant feedback, and view their final score.

The system is built around two main classes: Question and QuizGame. The Question class stores question details, options, and correct answers, while the QuizGame class manages quiz execution, user interaction, answer validation, and score calculation.

Features:

Multiple-choice questions
Automatic answer checking
Instant feedback
Score tracking
Simple and interactive console interface
Modular and reusable OOP design

Benefits:

Reduces manual quiz evaluation time
Provides immediate results and feedback
Improves user engagement and learning experience
Demonstrates practical implementation of OOP concepts
Easy to extend with more questions and advanced features

Technologies Used:

C++
Object-Oriented Programming (OOP)
Classes and Objects
Encapsulation
Functions and Modular Design

Code:
#include <iostream>
#include <string>
using namespace std;

class Question {
private:
    string question;
    string optionA, optionB, optionC, optionD;
    char correctAnswer;

public:
    Question(string q, string a, string b,
             string c, string d, char answer) {
        question = q;
        optionA = a;
        optionB = b;
        optionC = c;
        optionD = d;
        correctAnswer = answer;
    }

    void displayQuestion() {
        cout << "\n" << question << endl;
        cout << "A. " << optionA << endl;
        cout << "B. " << optionB << endl;
        cout << "C. " << optionC << endl;
        cout << "D. " << optionD << endl;
    }

    bool checkAnswer(char userAnswer) {
        return (toupper(userAnswer) == toupper(correctAnswer));
    }
};

int main() {
    int score = 0;
    char answer;

    Question q1(
        "1. What is the capital of Pakistan?",
        "Karachi", "Lahore", "Islamabad", "Peshawar", 'C');

    Question q2(
        "2. Which language is used for OOP?",
        "C++", "HTML", "SQL", "CSS", 'A');

    Question q3(
        "3. How many days are there in a week?",
        "5", "6", "7", "8", 'C');

    Question quiz[] = {q1, q2, q3};

    cout << "==================================" << endl;
    cout << "      QUIZ GAME SYSTEM" << endl;
    cout << "==================================" << endl;

    for (int i = 0; i < 3; i++) {
        quiz[i].displayQuestion();

        cout << "Enter your answer (A/B/C/D): ";
        cin >> answer;

        if (quiz[i].checkAnswer(answer)) {
            cout << "Correct Answer!" << endl;
            score++;
        } else {
            cout << "Wrong Answer!" << endl;
        }
    }

    cout << "\n==================================" << endl;
    cout << "Quiz Completed!" << endl;
    cout << "Your Score: " << score << " / 3" << endl;

    if (score == 3)
        cout << "Excellent!" << endl;
    else if (score == 2)
        cout << "Good Job!" << endl;
    else
        cout << "Keep Practicing!" << endl;

    cout << "==================================" << endl;

    return 0;
}