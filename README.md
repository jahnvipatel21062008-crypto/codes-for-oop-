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

  #include <bits/stdc++.h>
using namespace std;

// 2(a)
class City {
public:
    string name;
    long population;
    void accept() {
        cout << "Enter city name:\n";
        cin.ignore();
        getline(cin, name);
        cout << "Enter population:\n";
        cin >> population;
    }
};

void cityProgram() {
    City c[5];
    for (int i = 0; i < 5; i++) {
        cout << "\nEnter details for city " << i + 1 << ":\n";
        c[i].accept();
    }
    long maxpop = c[0].population;
    string cname = c[0].name;
    for (int i = 1; i < 5; i++) {
        if (c[i].population > maxpop) {
            maxpop = c[i].population;
            cname = c[i].name;
        }
    }
    cout << "City with highest population: " << cname << "\n";
}

// 2(b)
class Account {
public:
    int acc_no;
    float balance;
    void accept() {
        cout << "Enter account number:\n";
        cin >> acc_no;
        cout << "Enter balance:\n";
        cin >> balance;
    }
    void addInterest() {
        if (balance >= 5000) balance += balance * 0.10f;
    }
    void display() {
        cout << "Account No: " << acc_no << " Balance: " << balance << "\n";
    }
};

void accountProgram() {
    Account a[10];
    for (int i = 0; i < 10; i++) {
        cout << "\nEnter details for account " << i + 1 << ":\n";
        a[i].accept();
    }
    for (int i = 0; i < 10; i++) {
        a[i].addInterest();
        a[i].display();
    }
}

// 2(c)
class Staff {
public:
    string name, post;
    void accept() {
        cout << "Enter name:\n";
        cin.ignore();
        getline(cin, name);
        cout << "Enter post:\n";
        getline(cin, post);
    }
};

void staffProgram() {
    Staff s[5];
    for (int i = 0; i < 5; i++) {
        cout << "\nEnter details for staff " << i + 1 << ":\n";
        s[i].accept();
    }
    cout << "Staff who are HOD:\n";
    for (int i = 0; i < 5; i++) {
        if (s[i].post == "HOD" || s[i].post == "hod" || s[i].post == "Hod")
            cout << s[i].name << "\n";
    }
}

int main() {
    cout << "Program 2(a)\n";
    cityProgram();

    cout << "\nProgram 2(b)\n";
    accountProgram();

    cout << "\nProgram 2(c)\n";
    staffProgram();

    return 0;
}

 #include <bits/stdc++.h>
using namespace std;

// 3(a)
class Book {
public:
    string book_title, author_name;
    float price;
    void accept() {
        cout << "Enter book title:\n";
        cin.ignore();
        getline(cin, book_title);
        cout << "Enter author name:\n";
        getline(cin, author_name);
        cout << "Enter price:\n";
        cin >> price;
    }
    void display() {
        cout << "Book Title: " << book_title << "\n";
        cout << "Author Name: " << author_name << "\n";
        cout << "Price: " << price << "\n";
    }
};

// 3(b)
class Student {
public:
    int roll_no;
    float percentage;
    void accept() {
        cout << "Enter roll number:\n";
        cin >> roll_no;
        cout << "Enter percentage:\n";
        cin >> percentage;
    }
    void display() {
        cout << "Roll No: " << roll_no << "\n";
        cout << "Percentage: " << percentage << "\n";
    }
    void useThis() {
        this->display();
    }
};

// 3(c)
class Outer {
public:
    int x;
    class Inner {
    public:
        int y;
        void showInner() {
            cout << "Inner class value: " << y << "\n";
        }
    };
    void showOuter() {
        cout << "Outer class value: " << x << "\n";
    }
};

int main() {
    cout << "Program 3(a)\n";
    Book b, *ptr;
    ptr = &b;
    ptr->accept();
    ptr->display();

    cout << "\nProgram 3(b)\n";
    Student s;
    s.accept();
    s.useThis();

    cout << "\nProgram 3(c)\n";
    Outer o;
    Outer::Inner i;
    o.x = 10;
    i.y = 20;
    o.showOuter();
    i.showInner();

    return 0;
}

#include <bits/stdc++.h>
using namespace std;

// 4(a)
class Complex {
public:
    float real, imag;
    Complex() {}
    Complex(float r, float i) {
        real = r;
        imag = i;
    }
    Complex operator+(Complex c) {
        Complex temp;
        temp.real = real + c.real;
        temp.imag = imag + c.imag;
        return temp;
    }
    void display() {
        cout << "Sum: " << real << " + " << imag << "i\n";
    }
};

// 4(b)
class Distance {
public:
    int feet, inches;
    Distance() {}
    Distance(int f, int i) {
        feet = f;
        inches = i;
    }
    Distance operator-(Distance d) {
        Distance temp;
        int total1 = feet * 12 + inches;
        int total2 = d.feet * 12 + d.inches;
        int diff = abs(total1 - total2);
        temp.feet = diff / 12;
        temp.inches = diff % 12;
        return temp;
    }
    void display() {
        cout << "Difference: " << feet << " feet " << inches << " inches\n";
    }
};

// 4(c)
class Number {
public:
    int value;
    Number(int v) {
        value = v;
    }
    Number operator++() {
        ++value;
        return *this;
    }
    Number operator--() {
        --value;
        return *this;
    }
    void display() {
        cout << "Value: " << value << "\n";
    }
};

int main() {
    cout << "Program 4(a)\n";
    Complex c1(2.5, 3.5), c2(1.5, 2.5), c3;
    c3 = c1 + c2;
    c3.display();

    cout << "\nProgram 4(b)\n";
    Distance d1(5, 8), d2(3, 4), d3;
    d3 = d1 - d2;
    d3.display();

    cout << "\nProgram 4(c)\n";
    Number n(10);
    ++n;
    n.display();
    --n;
    n.display();

    return 0;
}

 #include <bits/stdc++.h>
using namespace std;

// 5(a)
class Test {
public:
    static int count;
    Test() {
        count++;
    }
    static void showCount() {
        cout << "Number of objects created: " << count << "\n";
    }
};
int Test::count = 0;

// 5(b)
class Number {
public:
    int a, b;
    void accept() {
        cout << "Enter two numbers:\n";
        cin >> a >> b;
    }
    friend int add(Number n);
};
int add(Number n) {
    return n.a + n.b;
}

// 5(c)
class Student {
public:
    int roll;
    string name;
    Student(int r, string n) {
        roll = r;
        name = n;
    }
    Student(Student &obj) {
        roll = obj.roll;
        name = obj.name;
    }
    void display() {
        cout << "Roll No: " << roll << "\n";
        cout << "Name: " << name << "\n";
    }
};

int main() {
    cout << "Program 5(a)\n";
    Test t1, t2, t3;
    Test::showCount();

    cout << "\nProgram 5(b)\n";
    Number n;
    n.accept();
    cout << "Sum: " << add(n) << "\n";

    cout << "\nProgram 5(c)\n";
    Student s1(1, "Jahnvi"), s2(s1);
    s1.display();
    s2.display();

    return 0;
}
#include <bits/stdc++.h>
using namespace std;

// 6(a)
class Shape {
public:
    virtual void area() {}
};
class Circle : public Shape {
public:
    float r;
    void accept() {
        cout << "Enter radius:\n";
        cin >> r;
    }
    void area() {
        cout << "Area of Circle: " << 3.14f * r * r << "\n";
    }
};
class Rectangle : public Shape {
public:
    float l, b;
    void accept() {
        cout << "Enter length and breadth:\n";
        cin >> l >> b;
    }
    void area() {
        cout << "Area of Rectangle: " << l * b << "\n";
    }
};

// 6(b)
class Vehicle {
public:
    void display() {
        cout << "This is a Vehicle\n";
    }
};
class Car : public Vehicle {
public:
    void display() {
        cout << "This is a Car\n";
    }
};
class Bike : public Vehicle {
public:
    void display() {
        cout << "This is a Bike\n";
    }
};

// 6(c)
class Base {
public:
    virtual void show() {
        cout << "Base class function\n";
    }
};
class Derived : public Base {
public:
    void show() {
        cout << "Derived class function\n";
    }
};

int main() {
    cout << "Program 6(a)\n";
    Circle c;
    Rectangle r;
    c.accept();
    r.accept();
    Shape *s;
    s = &c;
    s->area();
    s = &r;
    s->area();

    cout << "\nProgram 6(b)\n";
    Vehicle *v;
    Car car;
    Bike bike;
    v = &car;
    v->display();
    v = &bike;
    v->display();

    cout << "\nProgram 6(c)\n";
    Base *b;
    Derived d;
    b = &d;
    b->show();

    return 0;
}
#include <bits/stdc++.h>
using namespace std;

// 7(a)
class Student {
public:
    int roll;
    string name;
    Student() {
        roll = 0;
        name = "";
    }
    Student(int r, string n) {
        roll = r;
        name = n;
    }
    void display() {
        cout << "Roll: " << roll << " Name: " << name << "\n";
    }
};

// 7(b)
class Number {
public:
    int a, b;
    Number() {
        a = 0;
        b = 0;
    }
    Number(int x, int y) {
        a = x;
        b = y;
    }
    Number operator*(Number n) {
        Number temp;
        temp.a = a * n.a;
        temp.b = b * n.b;
        return temp;
    }
    void display() {
        cout << "Values: " << a << " " << b << "\n";
    }
};

// 7(c)
class Shape {
public:
    virtual void display() {}
};
class Circle : public Shape {
public:
    float r;
    Circle(float radius) {
        r = radius;
    }
    void display() {
        cout << "Area of Circle: " << 3.14f * r * r << "\n";
    }
};
class Square : public Shape {
public:
    float side;
    Square(float s) {
        side = s;
    }
    void display() {
        cout << "Area of Square: " << side * side << "\n";
    }
};

int main() {
    cout << "Program 7(a)\n";
    Student s1;
    Student s2(10, "Jahnvi");
    s1.display();
    s2.display();

    cout << "\nProgram 7(b)\n";
    Number n1(2, 3), n2(4, 5), n3;
    n3 = n1 * n2;
    n3.display();

    cout << "\nProgram 7(c)\n";
    Shape *ptr;
    Circle c(5);
    Square s(4);
    ptr = &c;
    ptr->display();
    ptr = &s;
    ptr->display();

    return 0;
}
#include <bits/stdc++.h>
using namespace std;

// 8(a)
class Item {
public:
    int code;
    float price;
    void getdata() {
        cout << "Enter item code and price:\n";
        cin >> code >> price;
    }
    void show() {
        cout << "Code: " << code << " Price: " << price << "\n";
    }
};

int main1() {
    vector<Item> items;
    int n;
    cout << "Enter number of items:\n";
    cin >> n;
    for (int i = 0; i < n; i++) {
        Item temp;
        temp.getdata();
        items.push_back(temp);
    }
    cout << "Items entered:\n";
    for (auto &x : items) x.show();
    return 0;
}

// 8(b)
int main2() {
    string s;
    cout << "Enter a string:\n";
    cin.ignore();
    getline(cin, s);
    reverse(s.begin(), s.end());
    cout << "Reversed string: " << s << "\n";
    return 0;
}

// 8(c)
int main3() {
    int n;
    cout << "Enter array size:\n";
    cin >> n;
    vector<int> arr(n);
    cout << "Enter elements:\n";
    for (int i = 0; i < n; i++) cin >> arr[i];
    sort(arr.begin(), arr.end());
    cout << "Sorted elements:\n";
    for (int x : arr) cout << x << " ";
    cout << "\n";
    return 0;
}

int main() {
    cout << "Program 8(a)\n";
    main1();

    cout << "\nProgram 8(b)\n";
    main2();

    cout << "\nProgram 8(c)\n";
    main3();

    return 0;
}
#include <bits/stdc++.h>
using namespace std;

// 9(a)
template <class T>
T add(T a, T b) {
    return a + b;
}

// 9(b)
template <class T>
void bubbleSort(vector<T> &arr) {
    for (int i = 0; i < arr.size() - 1; i++) {
        for (int j = 0; j < arr.size() - i - 1; j++) {
            if (arr[j] > arr[j + 1])
                swap(arr[j], arr[j + 1]);
        }
    }
}

// 9(c)
template <class T>
T findMax(T a, T b, T c) {
    if (a > b && a > c) return a;
    else if (b > c) return b;
    else return c;
}

int main() {
    cout << "Program 9(a)\n";
    cout << "Sum of integers: " << add(3, 5) << "\n";
    cout << "Sum of floats: " << add(2.5f, 3.6f) << "\n";

    cout << "\nProgram 9(b)\n";
    vector<int> arr = {5, 1, 4, 2, 8};
    bubbleSort(arr);
    cout << "Sorted elements:\n";
    for (int x : arr) cout << x << " ";
    cout << "\n";

    cout << "\nProgram 9(c)\n";
    cout << "Maximum among 10, 25, 15: " << findMax(10, 25, 15) << "\n";
    cout << "Maximum among 2.5, 7.5, 5.5: " << findMax(2.5, 7.5, 5.5) << "\n";

    return 0;
}
#include <bits/stdc++.h>
using namespace std;

// 10(a)
class Student {
public:
    int roll;
    string name;
    void getData() {
        cout << "Enter roll number:\n";
        cin >> roll;
        cin.ignore();
        cout << "Enter name:\n";
        getline(cin, name);
    }
    void showData() {
        cout << "Roll: " << roll << " Name: " << name << "\n";
    }
};

int main1() {
    ofstream fout("student.txt");
    Student s;
    s.getData();
    fout << s.roll << "\n" << s.name << "\n";
    fout.close();
    ifstream fin("student.txt");
    Student s2;
    fin >> s2.roll;
    fin.ignore();
    getline(fin, s2.name);
    fin.close();
    cout << "Data from file:\n";
    s2.showData();
    return 0;
}

// 10(b)
int main2() {
    ifstream fin("numbers.txt");
    ofstream fout("even.txt");
    int num;
    while (fin >> num) {
        if (num % 2 == 0)
            fout << num << "\n";
    }
    fin.close();
    fout.close();
    cout << "Even numbers written to even.txt\n";
    return 0;
}

// 10(c)
int main3() {
    string s;
    cout << "Enter a string:\n";
    cin.ignore();
    getline(cin, s);
    ofstream fout("string.txt");
    fout << s;
    fout.close();
    ifstream fin("string.txt");
    string content;
    getline(fin, content);
    fin.close();
    reverse(content.begin(), content.end());
    cout << "Reversed from file: " << content << "\n";
    return 0;
}

int main() {
    cout << "Program 10(a)\n";
    main1();

    cout << "\nProgram 10(b)\n";
    main2();

    cout << "\nProgram 10(c)\n";
    main3();

    return 0;
}
#include <bits/stdc++.h>
using namespace std;

// 11(a)
class ExceptionExample {
public:
    void divide() {
        int a, b;
        cout << "Enter two numbers:\n";
        cin >> a >> b;
        try {
            if (b == 0)
                throw b;
            cout << "Result: " << a / b << "\n";
        } catch (int) {
            cout << "Division by zero not allowed\n";
        }
    }
};

// 11(b)
class ArrayExample {
public:
    void access() {
        int n;
        cout << "Enter size of array:\n";
        cin >> n;
        vector<int> arr(n);
        cout << "Enter elements:\n";
        for (int i = 0; i < n; i++) cin >> arr[i];
        try {
            int pos;
            cout << "Enter position to access:\n";
            cin >> pos;
            if (pos < 0 || pos >= n)
                throw pos;
            cout << "Element: " << arr[pos] << "\n";
        } catch (int) {
            cout << "Invalid array index\n";
        }
    }
};

// 11(c)
class AgeCheck {
public:
    void check() {
        int age;
        cout << "Enter your age:\n";
        cin >> age;
        try {
            if (age < 18)
                throw age;
            cout << "Eligible for voting\n";
        } catch (int) {
            cout << "Not eligible for voting\n";
        }
    }
};

int main() {
    cout << "Program 11(a)\n";
    ExceptionExample e;
    e.divide();

    cout << "\nProgram 11(b)\n";
    ArrayExample a;
    a.access();

    cout << "\nProgram 11(c)\n";
    AgeCheck c;
    c.check();

    return 0;
}
#include <bits/stdc++.h>
using namespace std;

// 12(a)
class Student {
public:
    int roll;
    string name;
    void accept() {
        cout << "Enter roll number:\n";
        cin >> roll;
        cin.ignore();
        cout << "Enter name:\n";
        getline(cin, name);
    }
    void display() {
        cout << "Roll: " << roll << " Name: " << name << "\n";
    }
};

// 12(b)
class Marks : public Student {
public:
    int sub1, sub2, sub3;
    void acceptMarks() {
        cout << "Enter marks of 3 subjects:\n";
        cin >> sub1 >> sub2 >> sub3;
    }
    int total() {
        return sub1 + sub2 + sub3;
    }
};

// 12(c)
class Result : public Marks {
public:
    float per;
    void calculate() {
        per = (total() / 3.0f);
    }
    void show() {
        display();
        cout << "Total: " << total() << "\n";
        cout << "Percentage: " << per << "%\n";
    }
};

int main() {
    cout << "Program 12(a,b,c)\n";
    Result r;
    r.accept();
    r.acceptMarks();
    r.calculate();
    r.show();
    return 0;
}
