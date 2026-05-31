# 📘 Day 9 — Functions & Function Overloading

> **GFG Curriculum Reference:** Day 9-12 (Part 1)

---

## 🔍 What is a Function?

A function is a **reusable block of code** that performs a specific task. It promotes modularity and avoids repetition.

---

## 📝 Function Syntax

```cpp
return_type function_name(parameters) {
    // body
    return value;
}
```

---

## Types of Functions

### 1. No parameters, no return value
```cpp
void greet() {
    cout << "Hello!" << endl;
}
greet();  // call
```

### 2. With parameters, with return value
```cpp
int add(int a, int b) {
    return a + b;
}
cout << add(3, 7);  // 10
```

### 3. Pass by Value (copy — original unchanged)
```cpp
void doubleIt(int x) {
    x = x * 2;  // local copy only
}
int n = 5;
doubleIt(n);
cout << n;  // still 5
```

### 4. Pass by Reference (original is modified)
```cpp
void doubleIt(int &x) {
    x = x * 2;  // modifies the original
}
int n = 5;
doubleIt(n);
cout << n;  // 10
```

### 5. Pass by Pointer
```cpp
void doubleIt(int *x) {
    *x = *x * 2;
}
int n = 5;
doubleIt(&n);
cout << n;  // 10
```

---

## 🔁 Function Prototype (Forward Declaration)

Needed when calling a function before its definition.

```cpp
int add(int, int);      // prototype (parameter names optional)

int main() {
    cout << add(3, 4);  // works even though add is defined below
}

int add(int a, int b) {
    return a + b;
}
```

---

## 📋 Default Arguments

```cpp
int power(int base, int exp = 2) {
    int result = 1;
    for (int i = 0; i < exp; i++) result *= base;
    return result;
}

cout << power(3);    // 9  (exp defaults to 2)
cout << power(3, 3); // 27
```

> Default arguments must be **rightmost** parameters.

---

## 🔄 Function Overloading

Same function name, **different parameter types or count**. Compiler selects based on call.

```cpp
int add(int a, int b) {
    return a + b;
}

double add(double a, double b) {
    return a + b;
}

string add(string a, string b) {
    return a + b;
}

cout << add(3, 4)           << endl;  // 7
cout << add(3.1, 4.2)       << endl;  // 7.3
cout << add("Hi", " World") << endl;  // Hi World
```

---

## 🪞 Inline Functions

For small, frequently-called functions — avoids function call overhead.

```cpp
inline int square(int x) {
    return x * x;
}
cout << square(5);  // 25
```

---

## 🔂 Recursion

A function calling itself. Must have a **base case**.

```cpp
// Factorial
int factorial(int n) {
    if (n == 0 || n == 1) return 1;  // base case
    return n * factorial(n - 1);     // recursive case
}
cout << factorial(5);  // 120
```

```cpp
// Fibonacci
int fib(int n) {
    if (n <= 1) return n;
    return fib(n - 1) + fib(n - 2);
}
cout << fib(7);  // 13
```

---

## ✅ Practice Tasks
1. Write an overloaded function `area()` for circle, rectangle, and triangle.
2. Write a recursive function to compute the sum of digits of a number.
3. Implement binary search recursively.
4. Write `isPalindrome(string s)` using recursion.

---

## 📌 GFG Resources
- [Functions in C++](https://www.geeksforgeeks.org/cpp/functions-in-cpp/)
- [Function Overloading](https://www.geeksforgeeks.org/cpp/function-overloading-c/)