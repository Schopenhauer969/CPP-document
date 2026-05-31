# 🚀 មគ្គុទ្ទេសក៍ C++ តាំងពីដំបូងដល់កម្រិតខ្ពស់
# C++ Complete Guide — Beginner to Advanced

> **ភាសា:** ខ្មែរ + English | **កម្រិត:** Beginner → Advanced 

---

## 📋 តារាងមាតិកា / Table of Contents

- [1. ការណែនាំ / Introduction](#1-ការណែនាំ--introduction)
- [2. មូលដ្ឋាន / Basics](#2-មូលដ្ឋាន--basics)
- [3. អថេរ និង ប្រភេទទិន្នន័យ / Variables & Data Types](#3-អថេរ-និង-ប្រភេទទិន្នន័យ--variables--data-types)
- [4. លក្ខខណ្ឌ / Conditionals](#4-លក្ខខណ្ឌ--conditionals)
- [5. រង្វិលជុំ / Loops](#5-រង្វិលជុំ--loops)
- [6. អនុគមន៍ / Functions](#6-អនុគមន៍--functions)
- [7. អារេ និង Vector / Arrays & Vectors](#7-អារេ-និង-vector--arrays--vectors)
- [8. Pointer និង Reference](#8-pointer-និង-reference)
- [9. Class និង Object (OOP)](#9-class-និង-object-oop)
- [10. Inheritance និង Polymorphism](#10-inheritance-និង-polymorphism)
- [11. Template](#11-template)
- [12. Exception Handling](#12-exception-handling)
- [13. STL (Standard Template Library)](#13-stl-standard-template-library)
- [14. Modern C++ (C++11/14/17/20)](#14-modern-c-c111417-20)

---

## 1. ការណែនាំ / Introduction

> **ខ្មែរ:** C++ គឺជាភាសាកម្មវិធីដែលមានល្បឿនលឿន និងអាចគ្រប់គ្រងធនធានបានដោយផ្ទាល់។ វាត្រូវបានប្រើក្នុង game engines, operating systems, embedded systems, និង high-performance applications។

> **English:** C++ is a powerful, compiled language with direct hardware control. It's used in games, OS development, embedded systems, and performance-critical software.

### ការដំឡើង / Setup

```bash
# Linux/macOS
sudo apt install g++        # Ubuntu/Debian
brew install gcc            # macOS

# Windows → Install MinGW or Visual Studio

# ការចងក្រង / Compile & Run
g++ -std=c++17 -o program main.cpp
./program
```

---

## 2. មូលដ្ឋាន / Basics

> **ខ្មែរ:** កម្មវិធី C++ គ្រប់ទាំងអស់ចាប់ផ្ដើមពី `main()` ។ `#include` គឺជាការដាក់បញ្ចូល library ។ `cout` ប្រើសម្រាប់បង្ហាញអត្ថបទ។

```cpp
#include <iostream>   // បញ្ចូល library សម្រាប់ input/output
using namespace std;  // ប្រើ std namespace ដើម្បីសង្ខេបកូដ

int main() {
    // បង្ហាញអត្ថបទ / Print text
    cout << "Hello, World!" << endl;

    // ទទួលការបញ្ចូលពី user / Get user input
    string name;
    cout << "Enter your name: ";
    cin >> name;
    cout << "Hello, " << name << "!" << endl;

    return 0; // 0 = program ran successfully
}
```

**លទ្ធផល / Output:**
```
Hello, World!
Enter your name: Dara
Hello, Dara!
```

---

## 3. អថេរ និង ប្រភេទទិន្នន័យ / Variables & Data Types

> **ខ្មែរ:** អថេរ (Variable) គឺជាប្រអប់ដែលយើងប្រើដើម្បីរក្សាទុកទិន្នន័យ។ ប្រភេទទិន្នន័យ (Data Type) ប្រាប់ Computer ថាទិន្នន័យមានប្រភេទអ្វី។

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    // ———— ប្រភេទចំនួនគត់ / Integer Types ————
    int age       = 25;          // ចំនួនគត់ (-2B to +2B)
    short small   = 100;         // ចំនួនតូច (-32768 to 32767)
    long big      = 1000000L;    // ចំនួនធំ
    long long huge = 9999999999LL; // ចំនួនធំណាស់

    // ———— ចំនួនទសភាគ / Floating Point ————
    float  price  = 9.99f;       // ទសភាគ (7 digits precision)
    double pi     = 3.14159265;  // ទសភាគ (15 digits precision)

    // ———— តួអក្សរ / Characters ————
    char   grade  = 'A';         // តួអក្សរ 1  តួ
    string name   = "Sophea";    // ស្ទ្រីង (ពាក្យ/ប្រយោគ)

    // ———— Boolean (true/false) ————
    bool isPassed = true;        // true ឬ false

    // ———— auto (C++11) — ទុក compiler ជ្រើសប្រភេទ ————
    auto score    = 98.5;        // compiler ដឹងថា double

    // ———— Constants — តម្លៃដែលមិនអាចផ្លាស់ប្ដូរ ————
    const int MAX_SIZE = 100;    // ✅ ត្រូវ
    // MAX_SIZE = 200;           // ❌ Error! const មិនអាចផ្លាស់ប្ដូរ

    cout << "Name: "    << name     << endl;
    cout << "Age: "     << age      << endl;
    cout << "Price: $"  << price    << endl;
    cout << "Passed: "  << boolalpha << isPassed << endl;

    return 0;
}
```

### ទំហំប្រភេទទិន្នន័យ / Data Type Sizes

| ប្រភេទ / Type | ទំហំ / Size | ជួរ / Range |
|---|---|---|
| `bool` | 1 byte | true / false |
| `char` | 1 byte | -128 to 127 |
| `int` | 4 bytes | ±2,147,483,647 |
| `float` | 4 bytes | ±3.4 × 10³⁸ |
| `double` | 8 bytes | ±1.7 × 10³⁰⁸ |
| `long long` | 8 bytes | ±9.2 × 10¹⁸ |

---

## 4. លក្ខខណ្ឌ / Conditionals

> **ខ្មែរ:** ការធ្វើការសម្រេចចិត្ត (Decision Making) — `if`, `else if`, `else` ប្រើដើម្បីកំណត់ល័ក្ខខ័ណ្ឌ។ `switch` ប្រើជំនួស `if-else` ច្រើន។

```cpp
#include <iostream>
using namespace std;

int main() {
    int score = 85;

    // ———— if / else if / else ————
    if (score >= 90) {
        cout << "Grade: A (ល្អឥតខ្ចោះ)" << endl;
    } else if (score >= 80) {
        cout << "Grade: B (ល្អ)" << endl;
    } else if (score >= 70) {
        cout << "Grade: C (មធ្យម)" << endl;
    } else {
        cout << "Grade: F (ធ្លាក់)" << endl;
    }

    // ———— Ternary Operator (if-else តែ 1 បន្ទាត់) ————
    string result = (score >= 50) ? "Pass ✅" : "Fail ❌";
    cout << result << endl;

    // ———— switch statement ————
    char grade = 'B';
    switch (grade) {
        case 'A':
            cout << "Excellent!" << endl;
            break;
        case 'B':
            cout << "Good job!" << endl;  // ← នឹងប្រតិបត្តិ
            break;
        case 'C':
            cout << "Average" << endl;
            break;
        default:
            cout << "Invalid grade" << endl;
    }

    return 0;
}
```

---

## 5. រង្វិលជុំ / Loops

> **ខ្មែរ:** រង្វិលជុំ (Loop) ប្រើដើម្បីធ្វើការរ ซ้ำ ● `for` — ប្រើពេលដឹងចំនួនដង ● `while` — ប្រើពេលមិនដឹងចំនួន ● `do-while` — ប្រតិបត្តិយ៉ាងហោចណាស់ 1 ដង

```cpp
#include <iostream>
using namespace std;

int main() {

    // ———— for loop ————
    // ខ្មែរ: រង្វិលជុំ for ប្រើសម្រាប់ loop ចំនួនដងជាក់លាក់
    cout << "=== for loop ===" << endl;
    for (int i = 1; i <= 5; i++) {
        cout << "i = " << i << endl;
    }

    // ———— while loop ————
    // ខ្មែរ: while loop ប្រតិបត្តិតែពេល condition = true
    cout << "\n=== while loop ===" << endl;
    int count = 0;
    while (count < 3) {
        cout << "count = " << count << endl;
        count++;
    }

    // ———— do-while loop ————
    // ខ្មែរ: do-while loop ប្រតិបត្តិ 1 ដងជានិច្ច មុននឹងពិនិត្យ condition
    cout << "\n=== do-while loop ===" << endl;
    int num = 10;
    do {
        cout << "num = " << num << endl;
        num++;
    } while (num < 10); // condition false ប៉ុន្តែ ប្រតិបត្តិ 1 ដងហើយ

    // ———— Range-based for (C++11) ————
    // ខ្មែរ: ស្ងួនងាយដើម្បី loop តាម array ឬ vector
    cout << "\n=== range-based for ===" << endl;
    int nums[] = {10, 20, 30, 40, 50};
    for (int n : nums) {
        cout << n << " ";
    }
    cout << endl;

    // ———— break & continue ————
    cout << "\n=== break & continue ===" << endl;
    for (int i = 1; i <= 10; i++) {
        if (i == 4) continue;  // រំលង 4 / Skip 4
        if (i == 7) break;     // ឈប់នៅ 7 / Stop at 7
        cout << i << " ";
    }
    // Output: 1 2 3 5 6

    return 0;
}
```

---

## 6. អនុគមន៍ / Functions

> **ខ្មែរ:** អនុគមន៍ (Function) ប្រើដើម្បីដាក់ប្រមូលកូដដែលធ្វើការដូចគ្នា ហើយអាចហៅប្រើម្ដងទៀតបាន។ នេះជួយបន្ថយការសរសេរកូដម្ដងទៀតទៀតតោ (DRY - Don't Repeat Yourself)។

```cpp
#include <iostream>
using namespace std;

// ———— Function Declaration & Definition ————
// ទម្រង់: return_type functionName(parameters) { body }

// អនុគមន៍ without return value (void)
void greet(string name) {
    cout << "Hello, " << name << "! 👋" << endl;
}

// អនុគមន៍ with return value
int add(int a, int b) {
    return a + b;
}

// Default parameters — parameter ដែលមានតម្លៃ default
double power(double base, int exp = 2) {
    double result = 1;
    for (int i = 0; i < exp; i++) result *= base;
    return result;
}

// Function Overloading — ឈ្មោះដូចគ្នា ប៉ុន្តែ parameter ខុសគ្នា
int multiply(int a, int b)       { return a * b; }
double multiply(double a, double b) { return a * b; }

// Pass by Reference — ប្ដូរតម្លៃ variable ដើម
void doubleValue(int& x) {
    x *= 2;  // ប្ដូរ variable ដើម
}

// Pass by Pointer
void tripleValue(int* x) {
    *x *= 3;
}

// Recursive Function — អនុគមន៍ហៅខ្លួនឯង
int factorial(int n) {
    if (n <= 1) return 1;         // Base case
    return n * factorial(n - 1); // Recursive case
}

int main() {
    greet("Sreymom");                      // Hello, Sreymom! 👋
    cout << add(3, 7) << endl;             // 10
    cout << power(3.0) << endl;            // 9 (default exp=2)
    cout << power(2.0, 10) << endl;        // 1024

    cout << multiply(4, 5) << endl;        // 20 (int version)
    cout << multiply(2.5, 3.0) << endl;    // 7.5 (double version)

    int val = 5;
    doubleValue(val);
    cout << val << endl;                   // 10 (ត្រូវបានប្ដូរ)

    tripleValue(&val);
    cout << val << endl;                   // 30

    cout << factorial(5) << endl;          // 120 (5! = 5×4×3×2×1)

    return 0;
}
```

---

## 7. អារេ និង Vector / Arrays & Vectors

> **ខ្មែរ:** Array ជាបញ្ជីទិន្នន័យដែលមានប្រភេទដូចគ្នា ហើយមានទំហំថេរ។ Vector ដូច Array ដែរ ប៉ុន្តែអាចផ្លាស់ប្ដូរទំហំបាន (Dynamic)។

```cpp
#include <iostream>
#include <vector>
#include <algorithm>  // sort, find
using namespace std;

int main() {

    // ———— Static Array ————
    // ខ្មែរ: Array ដែលទំហំ fixed — មិនអាចបន្ថែម/ដកបាន
    int scores[5] = {95, 82, 78, 91, 68};

    // ចូលដំណើរការ element / Access elements
    cout << scores[0] << endl;  // 95 (index ចាប់ពី 0)
    cout << scores[4] << endl;  // 68 (element ចុងក្រោយ)

    // Loop តាម Array
    for (int i = 0; i < 5; i++) {
        cout << scores[i] << " ";
    }
    cout << endl;

    // ———— 2D Array (Matrix) ————
    // ខ្មែរ: Array 2 ជ្រុង — ដូច Table
    int matrix[2][3] = {
        {1, 2, 3},   // row 0
        {4, 5, 6}    // row 1
    };
    cout << matrix[1][2] << endl;  // 6 (row 1, col 2)

    // ———— Vector (Dynamic Array) ————
    // ខ្មែរ: Vector ដូច Array ប៉ុន្តែអាចបន្ថែម/ដក element ហើយ
    vector<int> v = {10, 20, 30};

    v.push_back(40);      // បន្ថែម 40 នៅចុង
    v.push_back(50);
    v.pop_back();         // ដក element ចុងក្រោយ (50)

    cout << "Size: " << v.size() << endl;    // 4
    cout << "First: " << v.front() << endl;  // 10
    cout << "Last: " << v.back() << endl;    // 40

    // Sort
    sort(v.begin(), v.end());  // 10 20 30 40

    // Range-based loop
    for (int x : v) cout << x << " ";
    cout << endl;

    // Vector of strings
    vector<string> names = {"Dara", "Sreymom", "Bopha"};
    names.insert(names.begin() + 1, "Sokha");  // បញ្ចូល "Sokha" ទី 2

    for (const string& n : names) cout << n << " ";
    cout << endl;

    return 0;
}
```

---

## 8. Pointer និង Reference

> **ខ្មែរ:** Pointer ជា variable ដែលរក្សាទុក **address** (អាសយដ្ឋាន) របស់ variable ផ្សេង។ Reference ក៏ស្រដៀងដែរ ប៉ុន្តែងាយស្រួលប្រើជាង។ ពួកវាជួយក្នុងការគ្រប់គ្រង memory ដោយផ្ទាល់។

```cpp
#include <iostream>
using namespace std;

int main() {

    // ———— Reference ————
    // ខ្មែរ: Reference = ឈ្មោះ alias ថ្មីសម្រាប់ variable ដដែល
    int x = 10;
    int& ref = x;     // ref គឺ alias របស់ x

    ref = 20;         // ប្ដូរ ref ក៏ប្ដូរ x ដែរ
    cout << x << endl;  // 20

    // ———— Pointer ————
    // ខ្មែរ: & = ទទួល address   * = ចូលដំណើរការ value ពី address
    int y = 42;
    int* ptr = &y;    // ptr ទុក address របស់ y

    cout << y     << endl;   // 42   (តម្លៃ y)
    cout << &y    << endl;   // 0x...  (address ក្នុង memory)
    cout << ptr   << endl;   // 0x...  (address ដែល ptr ទុក)
    cout << *ptr  << endl;   // 42   (dereference — ចូលដំណើរការ value)

    *ptr = 100;   // ប្ដូរ value តាមរយៈ pointer
    cout << y << endl;  // 100

    // ———— Dynamic Memory Allocation ————
    // ខ្មែរ: new = ស្នើ memory   delete = ប្ដូរ memory វិញ
    int* dynArr = new int[5];    // allocate array ក្នុង heap

    for (int i = 0; i < 5; i++) dynArr[i] = i * 10;
    for (int i = 0; i < 5; i++) cout << dynArr[i] << " ";
    cout << endl;  // 0 10 20 30 40

    delete[] dynArr;  // ⚠️ MUST free memory — បើមិនដូច្នេះ memory leak!

    // ———— Null Pointer ————
    int* nullPtr = nullptr;   // ✅ C++11 — គ្មាន address
    if (nullPtr == nullptr) {
        cout << "Pointer is null (safe)" << endl;
    }

    // ———— Smart Pointer (C++11) — ល្អបំផុតដើម្បីជៀសវាងការភ្លេច delete ————
    // (ត្រូវ #include <memory>)
    // unique_ptr<int> smart = make_unique<int>(99);
    // cout << *smart << endl;  // 99
    // auto-deleted when out of scope ✅

    return 0;
}
```

---

## 9. Class និង Object (OOP)

> **ខ្មែរ:** OOP (Object-Oriented Programming) គឺជារចនាបថការសរសេរកូដ ដែលប្រើ Class ជា "ប្លង់" (Blueprint) ហើយ Object ជា "ផលិតផល" (Instance)។ OOP ជួយរៀបចំកូដ ធ្វើការ reuse ហើយ maintain ងាយ។

```cpp
#include <iostream>
#include <string>
using namespace std;

class BankAccount {
private:  // ❌ មិនអាចចូលដំណើរការពីខាងក្រៅ (encapsulation)
    string owner;
    double balance;
    int    accountNumber;

public:   // ✅ អាចចូលដំណើរការពីខាងក្រៅ
    // Constructor — ហៅដោយស្វ័យប្រវត្តិពេល create object
    BankAccount(string name, double initialBalance, int accNum)
        : owner(name), balance(initialBalance), accountNumber(accNum) {
        cout << "Account created for " << owner << endl;
    }

    // Destructor — ហៅពេល object ត្រូវបានលុប
    ~BankAccount() {
        cout << "Account closed for " << owner << endl;
    }

    // Getter (accessor)
    string getOwner()   const { return owner; }
    double getBalance() const { return balance; }
    int    getAccNum()  const { return accountNumber; }

    // Methods
    void deposit(double amount) {
        if (amount <= 0) {
            cout << "Invalid amount!" << endl;
            return;
        }
        balance += amount;
        cout << "Deposited $" << amount << ". New balance: $" << balance << endl;
    }

    bool withdraw(double amount) {
        if (amount > balance) {
            cout << "Insufficient funds!" << endl;
            return false;
        }
        balance -= amount;
        cout << "Withdrew $" << amount << ". New balance: $" << balance << endl;
        return true;
    }

    void printInfo() const {
        cout << "━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━" << endl;
        cout << "Account #" << accountNumber          << endl;
        cout << "Owner:   " << owner                  << endl;
        cout << "Balance: $" << balance               << endl;
        cout << "━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━" << endl;
    }
};

int main() {
    // Create objects
    BankAccount acc1("Dara Sok",   1000.0, 10001);
    BankAccount acc2("Sophea Kim",  500.0, 10002);

    acc1.deposit(250.0);
    acc1.withdraw(100.0);
    acc1.printInfo();

    acc2.deposit(1000.0);
    acc2.withdraw(2000.0);  // Insufficient funds!

    return 0;
}
```

---

## 10. Inheritance និង Polymorphism

> **ខ្មែរ:** **Inheritance** អនុញ្ញាតឲ្យ Class មួយ (Child) ទទួលរូបសម្បត្តិ (property) និង method ពី Class មួយទៀត (Parent)។ **Polymorphism** ធ្វើឲ្យ method ដូចគ្នា មានប្រតិបត្តិការខុសគ្នាតាម object ប្រភេទ។

```cpp
#include <iostream>
#include <string>
#include <vector>
#include <memory>
using namespace std;

// ———— Base Class (Parent) ————
class Animal {
protected:
    string name;
    int    age;

public:
    Animal(string n, int a) : name(n), age(a) {}

    // virtual — អនុញ្ញាតឲ្យ child class override
    virtual void speak() const {
        cout << name << " makes a sound." << endl;
    }

    // Pure virtual — MUST be overridden in child class
    virtual string getType() const = 0;  // Abstract method

    virtual void info() const {
        cout << "[" << getType() << "] " << name << ", Age: " << age << endl;
    }

    virtual ~Animal() = default;  // Virtual destructor
};

// ———— Child Classes (Derived) ————
class Dog : public Animal {
    string breed;
public:
    Dog(string n, int a, string b) : Animal(n, a), breed(b) {}

    void speak() const override {  // override keyword = ប្រកាន់ safety
        cout << name << " says: Woof! 🐶" << endl;
    }

    string getType() const override { return "Dog"; }

    void fetch() const {
        cout << name << " fetches the ball! 🎾" << endl;
    }
};

class Cat : public Animal {
public:
    Cat(string n, int a) : Animal(n, a) {}

    void speak() const override {
        cout << name << " says: Meow! 🐱" << endl;
    }

    string getType() const override { return "Cat"; }
};

class Bird : public Animal {
public:
    Bird(string n, int a) : Animal(n, a) {}

    void speak() const override {
        cout << name << " says: Tweet! 🐦" << endl;
    }

    string getType() const override { return "Bird"; }
};

int main() {
    // Polymorphism — vector of base class pointers
    // ខ្មែរ: Animal* អាច point ទៅ Dog, Cat, Bird ណាក៏បាន
    vector<unique_ptr<Animal>> zoo;
    zoo.push_back(make_unique<Dog>("Buddy",  3, "Labrador"));
    zoo.push_back(make_unique<Cat>("Mimi",   2));
    zoo.push_back(make_unique<Bird>("Tweety", 1));
    zoo.push_back(make_unique<Dog>("Rex",    5, "German Shepherd"));

    cout << "=== Zoo Animals ===" << endl;
    for (const auto& animal : zoo) {
        animal->info();   // calls correct info()
        animal->speak();  // calls correct speak() — Polymorphism!
        cout << endl;
    }

    // Downcasting — ប្ដូរ back ទៅ child type
    Dog* dog = dynamic_cast<Dog*>(zoo[0].get());
    if (dog) dog->fetch();  // Dog-specific method

    return 0;
}
```

---

## 11. Template

> **ខ្មែរ:** Template ជួយឲ្យអ្នកសរសេរ function ឬ class ម្ដង ហើយប្រើបានជាមួយ data type ណាក៏បាន (int, double, string...)។ នេះជួយជៀសវាង code duplication។

```cpp
#include <iostream>
#include <vector>
#include <string>
using namespace std;

// ———— Function Template ————
// ខ្មែរ: T = placeholder សម្រាប់ type ណាក៏បាន
template <typename T>
T maxValue(T a, T b) {
    return (a > b) ? a : b;
}

// Template ជាមួយ multiple types
template <typename T, typename U>
void printPair(T first, U second) {
    cout << "(" << first << ", " << second << ")" << endl;
}

// ———— Class Template ————
template <typename T>
class Stack {
private:
    vector<T> data;

public:
    void push(const T& val) { data.push_back(val); }

    T pop() {
        if (empty()) throw runtime_error("Stack is empty!");
        T val = data.back();
        data.pop_back();
        return val;
    }

    T top()     const { return data.back(); }
    bool empty() const { return data.empty(); }
    int  size()  const { return data.size(); }
};

int main() {
    // Function template
    cout << maxValue(3, 7)         << endl;   // 7 (int)
    cout << maxValue(3.14, 2.71)   << endl;   // 3.14 (double)
    cout << maxValue('a', 'z')     << endl;   // z (char)

    printPair(1, "Hello");
    printPair(3.14, true);

    // Class template — Stack of int
    Stack<int> intStack;
    intStack.push(10);
    intStack.push(20);
    intStack.push(30);
    cout << intStack.pop() << endl;   // 30
    cout << intStack.top() << endl;   // 20

    // Stack of string
    Stack<string> strStack;
    strStack.push("Hello");
    strStack.push("World");
    cout << strStack.pop() << endl;   // World

    return 0;
}
```

---

## 12. Exception Handling

> **ខ្មែរ:** Exception Handling ជាការចាប់ Error ដែលកើតឡើងពេល runtime ដើម្បីការពារ program ពីការ crash ។ `try` ទទួល code ដែលអាច error, `throw` ចោល error, `catch` ចាប់ error។

```cpp
#include <iostream>
#include <stdexcept>
#include <string>
using namespace std;

// Custom Exception Class
class InsufficientFundsException : public exception {
    double amount;
public:
    InsufficientFundsException(double a) : amount(a) {}
    const char* what() const noexcept override {
        return "Insufficient funds in account!";
    }
    double getAmount() const { return amount; }
};

// Function ដែល throw exception
double divide(double a, double b) {
    if (b == 0) {
        throw invalid_argument("Cannot divide by zero! ❌");
    }
    return a / b;
}

void withdraw(double balance, double amount) {
    if (amount > balance) {
        throw InsufficientFundsException(amount - balance);
    }
    cout << "Withdrew $" << amount << " ✅" << endl;
}

int main() {

    // ———— Basic Exception Handling ————
    try {
        cout << divide(10.0, 2.0)  << endl;  // ✅ 5
        cout << divide(10.0, 0.0)  << endl;  // ❌ throws!
    }
    catch (const invalid_argument& e) {
        cout << "Error: " << e.what() << endl;
    }

    // ———— Multiple catch blocks ————
    try {
        string s = "hello";
        cout << s.at(100) << endl;   // throws out_of_range
    }
    catch (const out_of_range& e) {
        cout << "Out of range: " << e.what() << endl;
    }
    catch (const exception& e) {
        cout << "General error: " << e.what() << endl;
    }
    catch (...) {
        cout << "Unknown error!" << endl;   // ចាប់ error ណាក៏បាន
    }

    // ———— Custom Exception ————
    try {
        withdraw(100.0, 500.0);
    }
    catch (const InsufficientFundsException& e) {
        cout << "Error: " << e.what() << endl;
        cout << "Short by: $" << e.getAmount() << endl;
    }

    cout << "Program continues normally ✅" << endl;

    return 0;
}
```

---

## 13. STL (Standard Template Library)

> **ខ្មែរ:** STL ជាបណ្ណាល័យ C++ ដែលមានឧបករណ៍ (containers, algorithms) ដែល built-in ហើយ ready ប្រើ។ ជំនួសសរសេរ data structure ពីដំបូង ប្រើ STL ស្ទើរតែគ្រប់ case។

```cpp
#include <iostream>
#include <vector>
#include <map>
#include <set>
#include <queue>
#include <stack>
#include <algorithm>
#include <string>
using namespace std;

int main() {

    // ———— map (Key-Value Store) ————
    // ខ្មែរ: map ដូច dictionary — រក្សាទុក key: value
    map<string, int> studentScore;
    studentScore["Dara"]    = 95;
    studentScore["Sophea"]  = 88;
    studentScore["Bopha"]   = 72;
    studentScore["Makara"]  = 91;

    cout << "=== Scores ===" << endl;
    for (const auto& [name, score] : studentScore) {  // C++17 structured binding
        cout << name << ": " << score << endl;
    }

    // ———— set (Unique elements, sorted) ————
    // ខ្មែរ: set ស្រដៀង vector ប៉ុន្តែ auto-sorted និងគ្មាន duplicate
    set<int> uniqueNums = {5, 2, 8, 2, 1, 5, 9};
    cout << "\n=== Unique Sorted ===" << endl;
    for (int n : uniqueNums) cout << n << " ";  // 1 2 5 8 9
    cout << endl;

    // ———— queue (FIFO) ————
    // ខ្មែរ: queue = line រង់ចាំ — first in, first out
    queue<string> line;
    line.push("Customer 1");
    line.push("Customer 2");
    line.push("Customer 3");

    cout << "\n=== Queue (FIFO) ===" << endl;
    while (!line.empty()) {
        cout << "Serving: " << line.front() << endl;
        line.pop();
    }

    // ———— stack (LIFO) ————
    // ខ្មែរ: stack = ប៉ោង — last in, first out (ដូច undo operation)
    stack<string> history;
    history.push("Action 1");
    history.push("Action 2");
    history.push("Action 3");

    cout << "\n=== Stack (Undo) ===" << endl;
    while (!history.empty()) {
        cout << "Undoing: " << history.top() << endl;
        history.pop();
    }

    // ———— Algorithms ————
    // ខ្មែរ: STL algorithms ប្រើ iterator ដើម្បីធ្វើការជាមួយ containers
    vector<int> v = {64, 25, 12, 22, 11};

    sort(v.begin(), v.end());                    // sort ascending
    // sort(v.rbegin(), v.rend());               // sort descending

    auto it = find(v.begin(), v.end(), 22);
    if (it != v.end())
        cout << "\nFound 22 at index: " << (it - v.begin()) << endl;

    int total = 0;
    for (int x : v) total += x;
    // or: accumulate(v.begin(), v.end(), 0);

    cout << "Sum: " << total << endl;
    cout << "Max: " << *max_element(v.begin(), v.end()) << endl;
    cout << "Min: " << *min_element(v.begin(), v.end()) << endl;

    return 0;
}
```

---

## 14. Modern C++ (C++11/14/17/20)

> **ខ្មែរ:** C++ version ថ្មីៗ (C++11, C++14, C++17, C++20) បន្ថែម features ថ្មីៗ ដែលធ្វើឲ្យ code ខ្លី ងាយ មានសុវត្ថិភាព ហើយ powerful ជាងមុន។

```cpp
#include <iostream>
#include <vector>
#include <memory>
#include <functional>
#include <optional>
#include <string_view>
using namespace std;

int main() {

    // ———— Lambda Functions (C++11) ————
    // ខ្មែរ: Lambda = anonymous function (function គ្មានឈ្មោះ)
    auto greet = [](string name) {
        cout << "Hello, " << name << "!" << endl;
    };
    greet("Dara");

    // Lambda capture — ចាប់ variable ខាងក្រៅ
    int multiplier = 3;
    auto multiply = [multiplier](int x) { return x * multiplier; };
    cout << multiply(7) << endl;  // 21

    // Lambda ជាមួយ STL
    vector<int> nums = {1, 2, 3, 4, 5, 6, 7, 8};
    // remove_if: ដក element ដែល even ចេញ
    nums.erase(
        remove_if(nums.begin(), nums.end(), [](int n) { return n % 2 == 0; }),
        nums.end()
    );
    for (int n : nums) cout << n << " ";  // 1 3 5 7
    cout << endl;

    // ———— Smart Pointers (C++11) ————
    // ខ្មែរ: Smart pointer គ្រប់គ្រង memory ដោយស្វ័យប្រវត្តិ — no memory leaks!

    // unique_ptr: owner តែម្នាក់
    auto uptr = make_unique<int>(42);
    cout << *uptr << endl;  // 42
    // auto uptr2 = uptr;  // ❌ cannot copy unique_ptr

    // shared_ptr: ownership ចែករំលែកបាន
    auto sptr1 = make_shared<string>("Shared Resource");
    auto sptr2 = sptr1;  // ✅ both share ownership
    cout << *sptr1 << " | count: " << sptr1.use_count() << endl;  // count: 2

    // ———— Structured Bindings (C++17) ————
    // ខ្មែរ: unpack pair/tuple ឲ្យបានស្អាត
    pair<string, int> student = {"Sophea", 95};
    auto [name, score] = student;
    cout << name << ": " << score << endl;

    // ———— optional (C++17) ————
    // ខ្មែរ: optional = value ដែលអាច exist ឬ not exist (better than returning -1)
    auto findScore = [](string n) -> optional<int> {
        if (n == "Dara") return 98;
        return nullopt;  // not found
    };

    if (auto result = findScore("Dara")) {
        cout << "Score: " << *result << endl;
    }
    if (!findScore("Unknown")) {
        cout << "Student not found" << endl;
    }

    // ———— Range-based algorithms (C++20) ————
    // ខ្មែរ: C++20 ranges ងាយ និង អាចបញ្ចូលគ្នា (chainable)
    vector<int> data = {5, 2, 8, 1, 9, 3, 7, 4, 6};

    // C++17 way:
    sort(data.begin(), data.end());

    // ———— constexpr (Compile-time computation) ————
    constexpr int factorial(int n) {
        return (n <= 1) ? 1 : n * factorial(n - 1);
    }
    // constexpr int result = factorial(5);  // computed at compile time!

    return 0;
}
```

---

## 🧠 Best Practices / គន្លឹះល្អ

> **ខ្មែរ:** ច្បាប់ល្អក្នុងការសរសេរ C++ ស្អាត មានសុវត្ថិភាព ហើយ maintain បានងាយ

```cpp
// ✅ ល្អ — ប្រើ const ពេល variable មិនបំរែបំរួល
const int MAX_STUDENTS = 50;

// ✅ ល្អ — ប្រើ auto ពេល type ច្បាស់
auto it = myMap.find("key");

// ✅ ល្អ — ប្រើ nullptr ជំនួស NULL
int* ptr = nullptr;

// ✅ ល្អ — ប្រើ Smart Pointers ជំនួស raw new/delete
auto resource = make_unique<MyClass>();

// ✅ ល្អ — pass by const reference សម្រាប់ large objects
void process(const vector<int>& data);

// ✅ ល្អ — ប្រើ range-based for
for (const auto& item : container) { ... }

// ✅ ល្អ — ប្រើ override keyword
void myMethod() const override;

// ❌ មិនល្អ — avoid raw pointer ដោយគ្មាន smart pointer
// int* p = new int(5); // ងាយ memory leak

// ❌ មិនល្អ — avoid magic numbers
// if (score > 60) → ប្រើ const int PASSING_SCORE = 60;
```

---

## 📚 ធនធានបន្ថែម / Resources

| ប្រភព / Source | លីង / Link | ភាសា |
|---|---|---|
| cppreference.com | [cppreference.com](https://cppreference.com) | English |
| LearnCpp.com | [learncpp.com](https://www.learncpp.com) | English |
| CppCoreGuidelines | [isocpp.github.io](https://isocpp.github.io/CppCoreGuidelines) | English |
| Compiler Explorer | [godbolt.org](https://godbolt.org) | Online |

---

## 🗺️ ផ្លូវរៀន / Learning Roadmap

```
Beginner    ━━━━━━▶  Variables, Data Types, I/O
               ▼
Beginner+   ━━━━━━▶  Conditionals, Loops, Functions
               ▼
Intermediate━━━━━━▶  Arrays, Vectors, Pointers
               ▼
Intermediate+━━━━━▶  OOP (Class, Inheritance, Polymorphism)
               ▼
Advanced    ━━━━━━▶  Templates, STL, Exception Handling
               ▼
Advanced+   ━━━━━━▶  Modern C++11/17/20, Smart Pointers, Move Semantics
               ▼
Expert      ━━━━━━▶  Concurrency, Metaprogramming, Design Patterns
```

---

<div align="center">

**🇰🇭 ធ្វើឡើងដោយ / Made with ❤️ in Cambodia**

បើ Guide នេះមានប្រយោជន៍ — សូម ⭐ Star repository!

</div>
