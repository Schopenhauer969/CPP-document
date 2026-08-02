# ➕ C++ — Complete Guide (Beginner to Advanced)

> A complete, hands-on guide to C++ — from your first program to OOP, templates, the STL, and modern memory management used in real production code.

---

## 📚 Table of Contents

1. [Introduction](#1-introduction)
2. [Prerequisites & Setup](#2-prerequisites--setup)
3. [Your First C++ Program](#3-your-first-c-program)
4. [Variables & Data Types](#4-variables--data-types)
5. [Operators](#5-operators)
6. [Control Flow](#6-control-flow)
7. [Arrays & Vectors](#7-arrays--vectors)
8. [Strings](#8-strings)
9. [Functions](#9-functions)
10. [References & Pointers](#10-references--pointers)
11. [OOP: Classes & Objects](#11-oop-classes--objects)
12. [Inheritance & Polymorphism](#12-inheritance--polymorphism)
13. [Operator Overloading](#13-operator-overloading)
14. [Templates (Generic Programming)](#14-templates-generic-programming)
15. [The Standard Template Library (STL)](#15-the-standard-template-library-stl)
16. [Exception Handling](#16-exception-handling)
17. [Smart Pointers & Memory Management](#17-smart-pointers--memory-management)
18. [File I/O](#18-file-io)
19. [Lambda Expressions](#19-lambda-expressions)
20. [Best Practices](#20-best-practices)
21. [Full Example Project](#21-full-example-project)
22. [Resources](#22-resources)

---

## 1. Introduction

C++ is a compiled, statically-typed, multi-paradigm language built as an extension of C, adding object-oriented, generic, and functional programming features while keeping C's low-level performance and control.

**Key facts:**
- Compiles directly to machine code — extremely fast
- Supports procedural, object-oriented, and generic programming
- Manual and automatic (smart pointer) memory management options
- Powers game engines, browsers, operating systems, and high-frequency trading systems
- Current standard: **C++20** (C++23 emerging)

---

## 2. Prerequisites & Setup

- Basic understanding of C is helpful but not required
- A C++ compiler: **GCC (g++)**, **Clang**, or **MSVC**
- A code editor: **VS Code**, **CLion**

```bash
# Verify installation
g++ --version
```

**Compiling and running a C++ program:**

```bash
# Compile hello.cpp into an executable, using the C++20 standard
g++ -std=c++20 hello.cpp -o hello

# Run it
./hello        # Linux/macOS
hello.exe      # Windows
```

---

## 3. Your First C++ Program

```cpp
// hello.cpp
#include <iostream>

int main() {
    std::cout << "Hello, World!" << std::endl;
    return 0;
}
```

**Breaking it down:**

| Part | Meaning |
|---|---|
| `#include <iostream>` | Includes input/output stream support |
| `std::cout` | The standard output stream (console) |
| `<<` | The "insertion operator" — sends data into the stream |
| `std::endl` | Inserts a newline and flushes the output buffer |
| `return 0;` | Signals successful completion |

**Avoiding `std::` repetition:**

```cpp
#include <iostream>
using namespace std; // Brings all std:: names into scope (use carefully in large projects)

int main() {
    cout << "Hello, World!" << endl;
    return 0;
}
```

---

## 4. Variables & Data Types

```cpp
#include <iostream>

int main() {
    // Basic data types
    int age = 25;
    double price = 19.99;
    float temperature = 36.6f;
    char grade = 'A';
    bool isActive = true;       // C++ has a real boolean type, unlike C
    std::string name = "Sophea"; // Requires #include <string>

    // Constants
    const double PI = 3.14159;

    // Type inference with "auto" (C++11+) — compiler deduces the type
    auto count = 10;        // Inferred as int
    auto pi = 3.14;          // Inferred as double

    // Printing values
    std::cout << "Name: " << name << ", Age: " << age << std::endl;
    std::cout << "Pi: " << pi << std::endl;

    // sizeof — check type sizes
    std::cout << "Size of int: " << sizeof(int) << " bytes" << std::endl;

    // Type casting
    double d = 9.78;
    int i = static_cast<int>(d); // Modern, explicit cast (preferred over C-style casts)
    std::cout << i << std::endl; // 9

    return 0;
}
```

```cpp
#include <string>
// #include <string> is required to use std::string
```

---

## 5. Operators

```cpp
#include <iostream>

int main() {
    // Arithmetic
    std::cout << 10 + 5 << std::endl;   // 15
    std::cout << 10 / 3 << std::endl;    // 3 (integer division truncates)
    std::cout << 10.0 / 3 << std::endl;  // 3.33333
    std::cout << 10 % 3 << std::endl;    // 1

    // Comparison
    std::cout << (5 == 5) << std::endl;  // 1 (true)
    std::cout << (5 != 3) << std::endl;  // 1

    // Logical
    bool a = true, b = false;
    std::cout << (a && b) << std::endl;  // 0
    std::cout << (a || b) << std::endl;  // 1

    // Increment/decrement
    int count = 0;
    count++;
    ++count;
    std::cout << count << std::endl; // 2

    // String concatenation (works naturally with std::string, unlike C)
    std::string firstName = "Sophea";
    std::string lastName = "Chan";
    std::string fullName = firstName + " " + lastName;
    std::cout << fullName << std::endl; // "Sophea Chan"

    return 0;
}
```

---

## 6. Control Flow

```cpp
#include <iostream>

int main() {
    int score = 85;

    // if / else if / else
    if (score >= 90) {
        std::cout << "Grade: A" << std::endl;
    } else if (score >= 80) {
        std::cout << "Grade: B" << std::endl;
    } else {
        std::cout << "Grade: C or below" << std::endl;
    }

    // Ternary operator
    std::string status = (score >= 60) ? "Pass" : "Fail";

    // switch statement
    int day = 3;
    switch (day) {
        case 1:
            std::cout << "Monday" << std::endl;
            break;
        case 2:
            std::cout << "Tuesday" << std::endl;
            break;
        default:
            std::cout << "Another day" << std::endl;
            break;
    }

    // for loop
    for (int i = 0; i < 5; i++) {
        std::cout << "Iteration " << i << std::endl;
    }

    // Range-based for loop (C++11+, works with arrays and containers)
    int numbers[] = {1, 2, 3, 4, 5};
    for (int num : numbers) {
        std::cout << num << " ";
    }
    std::cout << std::endl;

    // while loop
    int n = 0;
    while (n < 3) {
        std::cout << "n = " << n << std::endl;
        n++;
    }

    // do-while loop
    int m = 0;
    do {
        std::cout << "m = " << m << std::endl;
        m++;
    } while (m < 3);

    return 0;
}
```

---

## 7. Arrays & Vectors

```cpp
#include <iostream>
#include <vector>
#include <array>

int main() {
    // C-style fixed-size array (size fixed at compile time, no bounds checking)
    int numbers[5] = {10, 20, 30, 40, 50};
    std::cout << numbers[0] << std::endl; // 10

    // std::array — a safer, modern fixed-size array (C++11+)
    std::array<int, 5> fixedArr = {1, 2, 3, 4, 5};
    std::cout << fixedArr.size() << std::endl; // 5

    // std::vector — dynamic, resizable array (the most commonly used container)
    std::vector<int> scores = {90, 85, 78};

    scores.push_back(95);           // Add to the end
    scores.pop_back();              // Remove the last element
    std::cout << scores[0] << std::endl;       // Access by index
    std::cout << scores.at(1) << std::endl;    // Access with bounds checking (throws if out of range)
    std::cout << scores.size() << std::endl;    // Number of elements

    // Looping through a vector
    for (int score : scores) {
        std::cout << score << " ";
    }
    std::cout << std::endl;

    // Iterating with an index
    for (size_t i = 0; i < scores.size(); i++) {
        std::cout << "Score " << i << ": " << scores[i] << std::endl;
    }

    // 2D vector
    std::vector<std::vector<int>> matrix = {
        {1, 2, 3},
        {4, 5, 6}
    };
    std::cout << matrix[1][2] << std::endl; // 6

    // Common vector operations
    std::vector<int> nums = {5, 3, 8, 1, 9};
    nums.insert(nums.begin() + 1, 100); // Insert 100 at index 1
    nums.erase(nums.begin());             // Remove the first element
    nums.clear();                          // Remove all elements
    std::cout << "Empty: " << nums.empty() << std::endl;

    return 0;
}
```

---

## 8. Strings

```cpp
#include <iostream>
#include <string>
#include <algorithm>

int main() {
    std::string message = "  Hello, C++ World!  ";

    std::cout << message.length() << std::endl;         // Length (including spaces)
    std::cout << message.substr(2, 5) << std::endl;      // "Hello" (start, length)
    std::cout << message.find("C++") << std::endl;        // Position of substring

    // Modifying strings
    std::string name = "sophea";
    std::transform(name.begin(), name.end(), name.begin(), ::toupper);
    std::cout << name << std::endl; // "SOPHEA"

    // Concatenation
    std::string greeting = "Hello, " + name + "!";
    std::cout << greeting << std::endl;

    // Comparing strings (works naturally with ==, unlike C's char arrays)
    std::string a = "hello";
    std::string b = "hello";
    std::cout << (a == b) << std::endl; // 1 (true)

    // Converting between strings and numbers
    std::string numStr = "42";
    int num = std::stoi(numStr);          // string to int
    std::string backToStr = std::to_string(num); // int to string

    // Iterating over characters
    for (char c : "Sophea") {
        std::cout << c;
    }
    std::cout << std::endl;

    // Splitting a string manually (C++ has no built-in split before C++20 ranges)
    std::string csv = "apple,banana,cherry";
    std::vector<std::string> parts;
    std::stringstream ss(csv); // Requires #include <sstream>
    std::string item;
    while (std::getline(ss, item, ',')) {
        parts.push_back(item);
    }
    for (const auto& part : parts) {
        std::cout << part << " ";
    }
    std::cout << std::endl;

    return 0;
}
```

---

## 9. Functions

```cpp
#include <iostream>

// Basic function
int add(int a, int b) {
    return a + b;
}

// Default parameters
std::string greet(std::string name, std::string greeting = "Hello") {
    return greeting + ", " + name + "!";
}

// Function overloading — same name, different parameter types
int multiply(int a, int b) {
    return a * b;
}
double multiply(double a, double b) {
    return a * b;
}

// Pass by reference (modifies the original variable, avoids copying)
void increment(int &value) {
    value++;
}

// Pass by const reference (avoids copying large objects, but prevents modification)
void printVector(const std::vector<int> &vec) {
    for (int v : vec) {
        std::cout << v << " ";
    }
    std::cout << std::endl;
}

// Recursive function
int factorial(int n) {
    if (n <= 1) return 1;
    return n * factorial(n - 1);
}

int main() {
    std::cout << add(3, 4) << std::endl;              // 7
    std::cout << greet("Sophea") << std::endl;          // "Hello, Sophea!"
    std::cout << multiply(3, 4) << std::endl;            // 12 (int version)
    std::cout << multiply(3.5, 2.0) << std::endl;         // 7.0 (double version)

    int x = 5;
    increment(x);
    std::cout << x << std::endl; // 6

    std::cout << factorial(5) << std::endl; // 120

    return 0;
}
```

---

## 10. References & Pointers

```cpp
#include <iostream>

int main() {
    // --- References --- (an alias for an existing variable, cannot be null or reassigned)
    int age = 25;
    int &ageRef = age; // ageRef is now another name for age

    ageRef = 26;
    std::cout << age << std::endl; // 26 — modifying the reference modifies the original

    // --- Pointers --- (store a memory address, can be null and reassigned)
    int *agePtr = &age; // Points to the address of age

    std::cout << *agePtr << std::endl;    // 26 — dereference to get the value
    std::cout << agePtr << std::endl;      // The memory address itself

    *agePtr = 27;
    std::cout << age << std::endl; // 27 — modifying through the pointer changes the original

    // nullptr (C++11+) — the modern, type-safe null pointer (prefer over C's NULL)
    int *emptyPtr = nullptr;
    if (emptyPtr == nullptr) {
        std::cout << "Pointer is null" << std::endl;
    }

    // References vs pointers:
    // - References must be initialized and can never be null or point elsewhere
    // - Pointers can be reassigned, can be null, and support pointer arithmetic
    // - Prefer references for function parameters when null isn't a valid case

    return 0;
}
```

---

## 11. OOP: Classes & Objects

```cpp
#include <iostream>
#include <string>

class Person {
private:
    std::string name; // Private — only accessible within the class
    int age;

public:
    // Constructor
    Person(std::string name, int age) : name(name), age(age) {
        // The "name(name), age(age)" part is a member initializer list — preferred over
        // assigning inside the body for performance and correctness
    }

    // Destructor — called automatically when the object is destroyed
    ~Person() {
        std::cout << name << " is being destroyed." << std::endl;
    }

    // Public methods
    std::string introduce() const { // "const" means this method doesn't modify the object
        return "Hi, I'm " + name + " and I'm " + std::to_string(age) + " years old.";
    }

    // Getters and setters
    std::string getName() const { return name; }
    int getAge() const { return age; }

    void setAge(int newAge) {
        if (newAge < 0) {
            throw std::invalid_argument("Age cannot be negative");
        }
        age = newAge;
    }
};

int main() {
    Person p1("Sophea", 25); // Stack-allocated object
    std::cout << p1.introduce() << std::endl;

    p1.setAge(26);
    std::cout << p1.getAge() << std::endl; // 26

    // Creating an object on the heap (requires manual cleanup, or better: smart pointers — see Section 17)
    Person *p2 = new Person("Dara", 30);
    std::cout << p2->introduce() << std::endl; // Use -> for pointer member access
    delete p2; // Must manually delete heap-allocated objects

    return 0;
} // p1 is automatically destroyed here (destructor runs)
```

**Access specifiers:**

| Specifier | Accessible from |
|---|---|
| `public` | Anywhere |
| `protected` | The class itself and derived (subclass) classes |
| `private` | Only the class itself |

---

## 12. Inheritance & Polymorphism

```cpp
#include <iostream>
#include <string>

class Animal {
protected:
    std::string name;

public:
    Animal(std::string name) : name(name) {}

    // virtual enables polymorphism — allows derived classes to override this method
    virtual std::string makeSound() const {
        return name + " makes a sound";
    }

    virtual ~Animal() {} // Virtual destructor — important when using polymorphism with pointers
};

class Dog : public Animal { // "public" inheritance — Dog IS-A Animal
private:
    std::string breed;

public:
    Dog(std::string name, std::string breed) : Animal(name), breed(breed) {}

    // override (C++11+) — explicitly marks this as overriding a virtual method (safer, catches typos)
    std::string makeSound() const override {
        return name + " barks! (a " + breed + ")";
    }

    std::string fetch() const {
        return name + " fetches the ball!";
    }
};

class Cat : public Animal {
public:
    Cat(std::string name) : Animal(name) {}

    std::string makeSound() const override {
        return name + " meows!";
    }
};

int main() {
    Dog dog("Rex", "Golden Retriever");
    std::cout << dog.makeSound() << std::endl; // "Rex barks! (a Golden Retriever)"
    std::cout << dog.fetch() << std::endl;

    // Polymorphism — using base class pointers to hold derived objects
    Animal *animals[3];
    animals[0] = new Dog("Max", "Poodle");
    animals[1] = new Cat("Whiskers");
    animals[2] = new Animal("Generic Creature");

    for (int i = 0; i < 3; i++) {
        std::cout << animals[i]->makeSound() << std::endl; // Calls the correct overridden version
        delete animals[i]; // Clean up heap memory
    }

    return 0;
}
```

---

## 13. Operator Overloading

```cpp
#include <iostream>

class Vector2D {
public:
    double x, y;

    Vector2D(double x = 0, double y = 0) : x(x), y(y) {}

    // Overloading the + operator
    Vector2D operator+(const Vector2D &other) const {
        return Vector2D(x + other.x, y + other.y);
    }

    // Overloading the == operator
    bool operator==(const Vector2D &other) const {
        return x == other.x && y == other.y;
    }

    // Overloading << to allow printing with std::cout directly
    friend std::ostream& operator<<(std::ostream &os, const Vector2D &v) {
        os << "(" << v.x << ", " << v.y << ")";
        return os;
    }
};

int main() {
    Vector2D v1(1, 2);
    Vector2D v2(3, 4);

    Vector2D sum = v1 + v2;         // Uses our overloaded operator+
    std::cout << sum << std::endl;  // Uses our overloaded operator<<: "(4, 6)"

    std::cout << (v1 == v2) << std::endl; // 0 (false)

    return 0;
}
```

---

## 14. Templates (Generic Programming)

```cpp
#include <iostream>
#include <string>

// Function template — works with any type
template <typename T>
T getMax(T a, T b) {
    return (a > b) ? a : b;
}

// Class template
template <typename T>
class Box {
private:
    T content;

public:
    Box(T content) : content(content) {}

    T getContent() const { return content; }
    void setContent(T newContent) { content = newContent; }
};

// Template with multiple type parameters
template <typename T, typename U>
class Pair {
public:
    T first;
    U second;

    Pair(T first, U second) : first(first), second(second) {}
};

int main() {
    std::cout << getMax(3, 7) << std::endl;         // 7 (T = int)
    std::cout << getMax(3.5, 2.1) << std::endl;       // 3.5 (T = double)
    std::cout << getMax<std::string>("apple", "banana") << std::endl; // "banana"

    Box<int> intBox(42);
    std::cout << intBox.getContent() << std::endl; // 42

    Box<std::string> stringBox("Hello");
    std::cout << stringBox.getContent() << std::endl; // "Hello"

    Pair<std::string, int> ageEntry("Sophea", 25);
    std::cout << ageEntry.first << " is " << ageEntry.second << std::endl;

    return 0;
}
```

---

## 15. The Standard Template Library (STL)

The STL provides ready-made containers, iterators, and algorithms.

```cpp
#include <iostream>
#include <vector>
#include <map>
#include <set>
#include <algorithm>
#include <numeric>

int main() {
    // --- vector --- (dynamic array, covered in Section 7)
    std::vector<int> nums = {5, 3, 8, 1, 9};

    // --- map --- (key-value pairs, sorted by key)
    std::map<std::string, int> ages;
    ages["Sophea"] = 25;
    ages["Dara"] = 30;
    ages.insert({"Bopha", 22});

    for (const auto &pair : ages) {
        std::cout << pair.first << ": " << pair.second << std::endl;
    }

    if (ages.find("Sophea") != ages.end()) {
        std::cout << "Found Sophea!" << std::endl;
    }

    // --- unordered_map --- (hash map, faster average lookup, no ordering)
    // #include <unordered_map>
    // std::unordered_map<std::string, int> fastLookup;

    // --- set --- (unique, sorted values)
    std::set<int> uniqueNumbers = {5, 3, 5, 1, 3};
    std::cout << uniqueNumbers.size() << std::endl; // 3 (duplicates removed)

    // --- Algorithms --- (work with iterators, apply to many container types)
    std::sort(nums.begin(), nums.end());               // Sort ascending
    std::sort(nums.begin(), nums.end(), std::greater<int>()); // Sort descending

    auto it = std::find(nums.begin(), nums.end(), 8);
    if (it != nums.end()) {
        std::cout << "Found 8 at position: " << (it - nums.begin()) << std::endl;
    }

    int total = std::accumulate(nums.begin(), nums.end(), 0); // Sum all elements
    std::cout << "Total: " << total << std::endl;

    int count = std::count_if(nums.begin(), nums.end(), [](int n) { return n > 5; });
    std::cout << "Count > 5: " << count << std::endl;

    std::vector<int> doubled;
    std::transform(nums.begin(), nums.end(), std::back_inserter(doubled),
                    [](int n) { return n * 2; });

    std::reverse(nums.begin(), nums.end());

    int maxVal = *std::max_element(nums.begin(), nums.end());
    int minVal = *std::min_element(nums.begin(), nums.end());

    return 0;
}
```

---

## 16. Exception Handling

```cpp
#include <iostream>
#include <stdexcept>

double divide(double a, double b) {
    if (b == 0) {
        throw std::invalid_argument("Cannot divide by zero");
    }
    return a / b;
}

// Custom exception class
class InsufficientFundsException : public std::runtime_error {
public:
    InsufficientFundsException(double balance, double amount)
        : std::runtime_error("Cannot withdraw " + std::to_string(amount) +
                              ", balance is only " + std::to_string(balance)) {}
};

double withdraw(double balance, double amount) {
    if (amount > balance) {
        throw InsufficientFundsException(balance, amount);
    }
    return balance - amount;
}

int main() {
    // try / catch / finally-equivalent (C++ uses RAII instead of "finally")
    try {
        std::cout << divide(10, 0) << std::endl;
    } catch (const std::invalid_argument &e) {
        std::cout << "Error: " << e.what() << std::endl;
    }

    // Catching multiple exception types
    try {
        withdraw(100, 150);
    } catch (const InsufficientFundsException &e) {
        std::cout << "Transaction failed: " << e.what() << std::endl;
    } catch (const std::exception &e) {
        // Catches any other standard exception
        std::cout << "Unexpected error: " << e.what() << std::endl;
    }

    // catch(...) catches literally anything (use as a last resort)
    try {
        throw 42; // Can throw any type in C++, not just exceptions
    } catch (...) {
        std::cout << "Caught something!" << std::endl;
    }

    return 0;
}
```

---

## 17. Smart Pointers & Memory Management

Modern C++ (C++11+) strongly prefers **smart pointers** over raw `new`/`delete` — they automatically free memory when no longer needed, preventing leaks.

```cpp
#include <iostream>
#include <memory>

class Resource {
public:
    Resource() { std::cout << "Resource acquired" << std::endl; }
    ~Resource() { std::cout << "Resource destroyed" << std::endl; }
    void use() { std::cout << "Using resource" << std::endl; }
};

int main() {
    // --- unique_ptr --- (exclusive ownership — only one pointer can own the resource)
    {
        std::unique_ptr<Resource> ptr1 = std::make_unique<Resource>();
        ptr1->use();
        // No need to call delete — automatically destroyed when ptr1 goes out of scope
    } // "Resource destroyed" printed here automatically

    // Transferring ownership (unique_ptr cannot be copied, only moved)
    std::unique_ptr<Resource> ptr2 = std::make_unique<Resource>();
    std::unique_ptr<Resource> ptr3 = std::move(ptr2); // Ownership moves to ptr3
    // ptr2 is now nullptr; using it would be undefined behavior

    // --- shared_ptr --- (shared ownership — reference-counted, freed when the last owner goes away)
    std::shared_ptr<Resource> shared1 = std::make_shared<Resource>();
    {
        std::shared_ptr<Resource> shared2 = shared1; // Both now share ownership
        std::cout << "Use count: " << shared1.use_count() << std::endl; // 2
    } // shared2 goes out of scope, but the resource isn't destroyed yet (shared1 still owns it)
    std::cout << "Use count: " << shared1.use_count() << std::endl; // 1

    // --- weak_ptr --- (non-owning reference to a shared_ptr's resource — avoids circular references)
    std::weak_ptr<Resource> weak1 = shared1;
    if (auto locked = weak1.lock()) { // Must "lock" to safely access it
        locked->use();
    }

    return 0;
} // All remaining smart pointers automatically clean up here
```

**Rule of thumb:** Prefer `unique_ptr` by default; use `shared_ptr` only when multiple owners genuinely need to share a resource. Avoid raw `new`/`delete` in modern C++ code entirely when possible.

---

## 18. File I/O

```cpp
#include <iostream>
#include <fstream>
#include <string>

int main() {
    // --- Writing to a file ---
    std::ofstream outFile("notes.txt"); // ofstream = output file stream
    if (outFile.is_open()) {
        outFile << "Hello, file world!" << std::endl;
        outFile << "Second line: " << 42 << std::endl;
        outFile.close();
    }

    // --- Appending to a file ---
    std::ofstream appendFile("notes.txt", std::ios::app);
    if (appendFile.is_open()) {
        appendFile << "Appended line." << std::endl;
        appendFile.close();
    }

    // --- Reading a file line by line ---
    std::ifstream inFile("notes.txt"); // ifstream = input file stream
    if (inFile.is_open()) {
        std::string line;
        while (std::getline(inFile, line)) {
            std::cout << line << std::endl;
        }
        inFile.close();
    } else {
        std::cout << "Unable to open file" << std::endl;
    }

    // --- Reading the whole file into a single string ---
    std::ifstream file2("notes.txt");
    std::string content((std::istreambuf_iterator<char>(file2)),
                          std::istreambuf_iterator<char>());
    std::cout << content << std::endl;

    return 0;
}
```

---

## 19. Lambda Expressions

```cpp
#include <iostream>
#include <vector>
#include <algorithm>

int main() {
    // Basic lambda — [] captures nothing, () params, {} body
    auto greet = []() {
        std::cout << "Hello from a lambda!" << std::endl;
    };
    greet();

    // Lambda with parameters and a return value
    auto add = [](int a, int b) -> int {
        return a + b;
    };
    std::cout << add(3, 4) << std::endl; // 7

    // Capturing outer variables by value [=] or by reference [&]
    int multiplier = 3;
    auto multiply = [multiplier](int n) { return n * multiplier; };
    std::cout << multiply(5) << std::endl; // 15

    int counter = 0;
    auto increment = [&counter]() { counter++; };
    increment();
    increment();
    std::cout << counter << std::endl; // 2

    // Using lambdas with STL algorithms (extremely common pattern)
    std::vector<int> numbers = {1, 2, 3, 4, 5};

    std::for_each(numbers.begin(), numbers.end(), [](int n) {
        std::cout << n * n << " ";
    });
    std::cout << std::endl;

    auto it = std::find_if(numbers.begin(), numbers.end(), [](int n) {
        return n > 3;
    });
    if (it != numbers.end()) {
        std::cout << "First number > 3: " << *it << std::endl;
    }

    std::sort(numbers.begin(), numbers.end(), [](int a, int b) {
        return a > b; // Descending order
    });

    return 0;
}
```

---

## 20. Best Practices

- ✅ Prefer `std::vector`/`std::array` over raw C-style arrays
- ✅ Use smart pointers (`unique_ptr`, `shared_ptr`) instead of raw `new`/`delete`
- ✅ Pass large objects by `const &` to avoid unnecessary copies
- ✅ Mark member functions `const` when they don't modify the object's state
- ✅ Use `override` when overriding virtual methods — catches typos at compile time
- ✅ Prefer `auto` when the type is obvious from context, for readability
- ✅ Use `nullptr` instead of `NULL` or `0` for pointers
- ✅ Follow the **Rule of Three/Five**: if you define a destructor, copy constructor, or copy assignment operator, you likely need all of them (or explicitly delete them)
- ✅ Enable warnings: compile with `-Wall -Wextra` and fix them
- ✅ Prefer STL algorithms (`std::sort`, `std::find`) over hand-written loops when they exist

---

## 21. Full Example Project

A simple **Inventory Management System** combining classes, STL containers, smart pointers, and exceptions:

```cpp
// Item.h
#ifndef ITEM_H
#define ITEM_H

#include <string>

class Item {
private:
    std::string name;
    double price;
    int quantity;

public:
    Item(std::string name, double price, int quantity)
        : name(name), price(price), quantity(quantity) {}

    std::string getName() const { return name; }
    double getPrice() const { return price; }
    int getQuantity() const { return quantity; }

    void addStock(int amount) { quantity += amount; }

    void removeStock(int amount) {
        if (amount > quantity) {
            throw std::runtime_error("Not enough stock for " + name);
        }
        quantity -= amount;
    }

    double totalValue() const { return price * quantity; }
};

#endif
```

```cpp
// Inventory.h
#ifndef INVENTORY_H
#define INVENTORY_H

#include <vector>
#include <memory>
#include <string>
#include <algorithm>
#include <stdexcept>
#include "Item.h"

class Inventory {
private:
    std::vector<std::unique_ptr<Item>> items;

public:
    void addItem(const std::string &name, double price, int quantity) {
        items.push_back(std::make_unique<Item>(name, price, quantity));
    }

    Item* findItem(const std::string &name) {
        auto it = std::find_if(items.begin(), items.end(),
            [&name](const std::unique_ptr<Item> &item) {
                return item->getName() == name;
            });

        if (it == items.end()) {
            throw std::runtime_error("Item not found: " + name);
        }
        return it->get();
    }

    double totalInventoryValue() const {
        double total = 0;
        for (const auto &item : items) {
            total += item->totalValue();
        }
        return total;
    }

    void printInventory() const {
        for (const auto &item : items) {
            std::cout << item->getName() << ": " << item->getQuantity()
                      << " units @ $" << item->getPrice() << std::endl;
        }
    }
};

#endif
```

```cpp
// main.cpp
#include <iostream>
#include "Inventory.h"

int main() {
    Inventory inventory;

    inventory.addItem("Laptop", 1200.00, 5);
    inventory.addItem("Mouse", 25.00, 50);
    inventory.addItem("Keyboard", 75.00, 30);

    std::cout << "--- Inventory ---" << std::endl;
    inventory.printInventory();

    try {
        Item *laptop = inventory.findItem("Laptop");
        laptop->removeStock(2);
        std::cout << "\nSold 2 laptops. Remaining: " << laptop->getQuantity() << std::endl;

        inventory.findItem("Monitor"); // Throws — doesn't exist
    } catch (const std::runtime_error &e) {
        std::cout << "\nError: " << e.what() << std::endl;
    }

    std::cout << "\nTotal inventory value: $" << inventory.totalInventoryValue() << std::endl;

    return 0;
} // All unique_ptr items are automatically cleaned up here
```

```bash
# Compile all files together
g++ -std=c++20 main.cpp -o inventory_manager -Wall -Wextra

# Run it
./inventory_manager
```

---

## 22. Resources

- C++ reference: `https://en.cppreference.com/w/cpp`
- ISO C++ official site: `https://isocpp.org/`
- Learn C++ (tutorial site): `https://www.learncpp.com/`

---

<p align="center">
  Made with ❤️ for developers learning C++.
</p>
