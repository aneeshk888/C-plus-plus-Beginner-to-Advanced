# 📘 Day 2 — Data Types & Variables in C++

> **GFG Curriculum Reference:** Day 2-3 (Part 1)

---

## 🔍 What are Data Types?

Data types specify the **type of data a variable can store**. The compiler allocates memory based on the declared data type.

---

## 🗂️ Primitive Data Types

### 1. `char` — Character (1 byte)
Stores a single character using ASCII values. Enclosed in single quotes.
```cpp
char c = 'A';
cout << c;      // A
cout << (int)c; // 65 (ASCII value)
```

### 2. `int` — Integer (4 bytes)
Stores whole numbers. Range: **-2,147,483,648 to 2,147,483,647**
```cpp
int x = 25;
cout << x;      // 25

int hex = 0x15; // hexadecimal
cout << hex;    // 21
```

### 3. `bool` — Boolean (1 byte)
Stores `true` (1) or `false` (0).
```cpp
bool isTrue = true;
cout << isTrue; // 1
```

### 4. `float` — Floating Point (4 bytes)
Stores decimal numbers. Range: **1.2e-38 to 3.4e+38**
```cpp
float f = 36.5;
cout << f; // 36.5
```

### 5. `double` — Double Precision (8 bytes)
Higher precision decimals. Range: **1.7e-308 to 1.7e+308**
```cpp
double pi = 3.1415926535;
cout << pi; // 3.14159
```

### 6. `void`
Represents absence of value. Used for functions that return nothing and void pointers.

---

## 📏 Size of All Data Types

```cpp
#include <iostream>
using namespace std;
int main() {
    cout << "char:   " << sizeof(char)   << " byte"  << endl;
    cout << "int:    " << sizeof(int)    << " bytes" << endl;
    cout << "float:  " << sizeof(float)  << " bytes" << endl;
    cout << "double: " << sizeof(double) << " bytes" << endl;
    cout << "bool:   " << sizeof(bool)   << " byte"  << endl;
    return 0;
}
```
**Output:**
```
char:   1 byte
int:    4 bytes
float:  4 bytes
double: 8 bytes
bool:   1 byte
```

---

## 📦 Variables in C++

A variable is a named memory location that stores a value.

### Declaration & Initialization
```cpp
int age = 20;           // declare + initialize
float gpa;              // declare only
gpa = 9.1;              // initialize later

int a, b, c;            // multiple declarations
int x = 1, y = 2, z = 3; // multiple with init
```

### Variable Naming Rules
- Can contain letters, digits, underscore `_`
- Must **start** with a letter or `_` (not a digit)
- Cannot be a **keyword** (`int`, `class`, `return`...)
- C++ is **case-sensitive** (`age` ≠ `Age`)

---

## 🔄 Type Conversion

### Implicit (Automatic)
```cpp
int n = 3;
char c = 'C';           // ASCII 67
int sum = n + c;        // char auto-converted to int
cout << sum;            // 70
```

### Explicit (Type Casting)
```cpp
double d = 3.99;
int i = (int)d;         // truncates to 3
cout << i;              // 3
```

---

## 💡 Type Safety
C++ is a **strongly typed** language — a variable's type is fixed at declaration.
```cpp
bool a = 10.248f;   // float assigned to bool
cout << a;          // prints 1 (not 10.248)
```

---

## ✅ Practice Tasks
1. Declare variables of all basic types and print their sizes using `sizeof`.
2. Check what happens when you assign a `float` to an `int` — what value do you get?
3. Print the ASCII values of letters A–Z using a `char` variable and a loop.

---

## 📌 GFG Resources
- [Data Types in C++](https://www.geeksforgeeks.org/cpp/cpp-data-types/)
- [Variables in C++](https://www.geeksforgeeks.org/cpp/cpp-variables/)
- [Type Conversion in C++](https://www.geeksforgeeks.org/cpp/type-conversion-in-c/)