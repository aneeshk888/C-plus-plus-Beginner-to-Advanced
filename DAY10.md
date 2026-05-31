# 📘 Day 10 — OOP: Classes, Objects & Constructors

> **GFG Curriculum Reference:** Day 9-12 (Part 2)

---

## 🔍 OOP Concepts Overview

| Pillar | Meaning |
|---|---|
| **Encapsulation** | Wrapping data + methods into a class, hiding internals |
| **Abstraction** | Showing only essential details, hiding complexity |
| **Inheritance** | Child class reuses and extends parent class |
| **Polymorphism** | Same interface, different behaviour |

---

## 🏗️ Defining a Class

```cpp
class Student {
private:                    // access specifier
    string name;
    int age;

public:
    // Constructor
    Student(string n, int a) : name(n), age(a) {}

    // Methods
    void display() {
        cout << "Name: " << name << ", Age: " << age << endl;
    }

    // Getter
    string getName() { return name; }
    int    getAge()  { return age;  }

    // Setter
    void setAge(int a) {
        if (a > 0) age = a;
    }
};

int main() {
    Student s1("Alice", 20);
    s1.display();               // Name: Alice, Age: 20
    s1.setAge(21);
    cout << s1.getAge();        // 21
}
```

---

## 🔒 Access Specifiers

| Specifier | Accessible From |
|---|---|
| `private` | Only within the class (default in `class`) |
| `public` | Anywhere |
| `protected` | Within class and derived classes |

---

## 🔧 Types of Constructors

### 1. Default Constructor
```cpp
class Box {
public:
    int length;
    Box() { length = 0; }         // default constructor
};
Box b;
cout << b.length;  // 0
```

### 2. Parameterized Constructor
```cpp
class Box {
public:
    int l, w, h;
    Box(int l, int w, int h) : l(l), w(w), h(h) {}
};
Box b(3, 4, 5);
```

### 3. Copy Constructor
```cpp
class Box {
public:
    int l;
    Box(int l) : l(l) {}
    Box(const Box &b) : l(b.l) {}  // copy constructor
};
Box b1(10);
Box b2 = b1;    // copy constructor called
```

---

## 💣 Destructor

Called automatically when an object goes out of scope.

```cpp
class MyClass {
public:
    MyClass()  { cout << "Created\n"; }
    ~MyClass() { cout << "Destroyed\n"; }
};

int main() {
    MyClass obj;    // prints "Created"
}   // prints "Destroyed" — destructor called here
```

---

## 🖇️ `this` Pointer

Points to the **current object**. Useful when parameter names shadow member names.

```cpp
class Counter {
    int count;
public:
    Counter(int count) {
        this->count = count;   // disambiguates
    }
    void show() { cout << this->count; }
};
```

---

## 📊 Static Members

Shared across all objects — not per-object.

```cpp
class Counter {
public:
    static int total;
    Counter() { total++; }
};
int Counter::total = 0;   // must define outside

int main() {
    Counter a, b, c;
    cout << Counter::total;  // 3
}
```

---

## ✅ Practice Tasks
1. Create a `BankAccount` class with `deposit`, `withdraw`, and `getBalance` methods.
2. Create a `Student` class with a static counter tracking how many students were created.
3. Write a `Rectangle` class with `area()` and `perimeter()` using a parameterized constructor.
4. Implement a deep copy constructor for a class containing a pointer member.

---

## 📌 GFG Resources
- [C++ Classes and Objects](https://www.geeksforgeeks.org/cpp/c-classes-and-objects/)
- [OOP in C++](https://www.geeksforgeeks.org/cpp/object-oriented-programming-in-cpp/)
- [Constructors in C++](https://www.geeksforgeeks.org/cpp/constructors-c/)