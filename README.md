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

#include <bits/stdc++.h>
using namespace std;

// 1(a)
class Student {
public:
    int roll_no;
    string name;
    string cls;
    void accept() {
        cout << "Enter roll number:\n";
        cin >> roll_no;
        cin.ignore();
        cout << "Enter name:\n";
        getline(cin, name);
        cout << "Enter class:\n";
        getline(cin, cls);
    }
    void display() {
        cout << "Roll No: " << roll_no << "\n";
        cout << "Name: " << name << "\n";
        cout << "Class: " << cls << "\n";
    }
};

// 1(b)
class Book {
public:
    string book_name;
    float price;
    int pages;
    void accept() {
        cout << "Enter book name:\n";
        cin.ignore();
        getline(cin, book_name);
        cout << "Enter price:\n";
        cin >> price;
        cout << "Enter number of pages:\n";
        cin >> pages;
    }
};

// 1(c)
class Time {
public:
    int hh, mm, ss;
    void accept() {
        cout << "Enter time in HH MM SS:\n";
        cin >> hh >> mm >> ss;
    }
    void display() {
        int total = hh * 3600 + mm * 60 + ss;
        cout << "Total seconds: " << total << "\n";
    }
};

int main() {
    cout << "Program 1(a)\n";
    Student s;
    s.accept();
    s.display();

    cout << "\nProgram 1(b)\n";
    Book b1, b2;
    b1.accept();
    b2.accept();
    cout << "Book with greater price:\n";
    if (b1.price > b2.price)
        cout << b1.book_name << "\n";
    else
        cout << b2.book_name << "\n";

    cout << "\nProgram 1(c)\n";
    Time t;
    t.accept();
    t.display();

    return 0;
}

