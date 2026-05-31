# 📘 Day 1 — Introduction to C++ Programming

> **GFG Curriculum Reference:** Day 1 — Introduction

---

## 🔍 What is C++?

C++ is a **general-purpose programming language** developed by **Bjarne Stroustrup** at Bell Labs in 1979 as an enhancement of C. Originally called **"C with Classes"**, it was renamed **C++** in 1983.

### Key Features
| Feature | Description |
|---|---|
| **Low-level Access** | Direct access to memory/system resources — great for OS, embedded systems, browsers |
| **Fast Execution** | One of the fastest high-level languages — used in game engines |
| **Object-Oriented** | Supports classes, inheritance, polymorphism for large-scale programs |

### C++ Evolution
`C with Classes (1979)` → `C++98` → `C++11` → `C++17` → `C++20` → `C++23`

---

## 🖥️ First C++ Program

```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "Hello, World!";
    return 0;
}
```
**Output:** `Hello, World!`

---

## 🏗️ Structure of a C++ Program

Every C++ program must follow this structure:

```
┌─────────────────────────────────┐
│  1. Header Files                │  #include <iostream>
│  2. Namespace Declaration       │  using namespace std;
│  3. Main Function               │  int main() { ... }
│  4. Statements                  │  cout << "Hello";
│  5. Return Statement            │  return 0;
└─────────────────────────────────┘
```

| Part | Syntax | Purpose |
|---|---|---|
| Header File | `#include <iostream>` | Includes input/output objects (cin, cout) |
| Namespace | `using namespace std;` | Avoids writing `std::` before every standard name |
| Main Function | `int main()` | Entry point — execution starts here |
| Comment (single) | `// comment` | Ignored by compiler, for documentation |
| Comment (multi) | `/* comment */` | Multi-line documentation |
| Statement | `cout << "Hi!";` | Executable code, ends with `;` |
| Return | `return 0;` | Signals successful program exit |

> **Common Headers:**
> - `<iostream>` — cin, cout
> - `<fstream>` — file I/O
> - `<string>` — string class
> - `<vector>` — STL vector
> - `<bits/stdc++.h>` — includes everything (competitive programming)

---

## ⚡ C vs C++ vs Java

| Feature | C | C++ | Java |
|---|---|---|---|
| Paradigm | Procedural | Multi-paradigm (OOP + Procedural) | OOP |
| Memory | Manual | Manual (`new`/`delete`) | Automatic (GC) |
| Speed | Fastest | Very fast | Moderate |
| OOP | ❌ | ✅ | ✅ |

---

## 🛠️ Setup & Compile

```bash
# Install (Ubuntu)
sudo apt install g++

# Compile
g++ hello.cpp -o hello

# Run
./hello
```

---

## ✅ Practice Tasks
1. Write and run a Hello World program.
2. Modify the program to print your name, college, and city on separate lines.
3. Explore what happens if you remove `return 0;` or a semicolon.

---

## 📌 GFG Resources
- [Introduction to C++](https://www.geeksforgeeks.org/cpp/cpp-programming-intro/)
- [Setting up C++ Environment](https://www.geeksforgeeks.org/cpp/setting-c-development-environment/)
- [C vs C++](https://www.geeksforgeeks.org/cpp/c-plus-plus/#C%20vs%20C++)
- [First C++ Program](https://www.geeksforgeeks.org/cpp/writing-first-c-program-hello-world-example/)