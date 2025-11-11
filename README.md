#include <bits/stdc++.h>
using namespace std;

class Student {
public:
    int roll_no;
    string name;
    string cls;
    void accept() {
        cout << "Enter roll number:\n";
        if (!(cin >> roll_no)) return;
        cin.ignore(numeric_limits<streamsize>::max(), '\n');
        cout << "Enter name:\n";
        getline(cin, name);
        cout << "Enter class:\n";
        getline(cin, cls);
    }
    void display() {
        cout << "Student details:\n";
        cout << "Roll No: " << roll_no << "\n";
        cout << "Name: " << name << "\n";
        cout << "Class: " << cls << "\n";
    }
};

class Book {
public:
    string book_name;
    double price;
    int pages;
    void accept() {
        cout << "Enter book name:\n";
        cin.ignore(numeric_limits<streamsize>::max(), '\n');
        getline(cin, book_name);
        cout << "Enter price:\n";
        cin >> price;
        cout << "Enter number of pages:\n";
        cin >> pages;
    }
};

class TimeHHMMSS {
public:
    int hh;
    int mm;
    int ss;
    void accept() {
        cout << "Enter time in HH:MM:SS format:\n";
        string t;
        cin.ignore(numeric_limits<streamsize>::max(), '\n');
        getline(cin, t);
        if (sscanf(t.c_str(), "%d:%d:%d", &hh, &mm, &ss) != 3) {
            hh = mm = ss = 0;
        }
    }
    long toSeconds() const {
        return hh * 3600L + mm * 60L + ss;
    }
    void displaySeconds() const {
        cout << "Total seconds: " << toSeconds() << "\n";
    }
};

int main() {
    Student s;
    s.accept();
    s.display();

    Book b1, b2;
    b1.accept();
    b2.accept();
    cout << "Book with greater price:\n";
    if (b1.price >= b2.price) {
        cout << b1.book_name << "\n";
    } else {
        cout << b2.book_name << "\n";
    }

    TimeHHMMSS t;
    t.accept();
    t.displaySeconds();

    return 0;
}
