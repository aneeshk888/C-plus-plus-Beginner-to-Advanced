# 📘 Day 5 — Loops & Jump Statements

> **GFG Curriculum Reference:** Day 4-5 (Part 2)

---

## 🔍 What are Loops?

Loops allow **repeated execution** of a code block as long as a condition is true. C++ has 3 types of loops.

---

## 1️⃣ `for` Loop

Use when the **number of iterations is known**.

```cpp
// Syntax
for (initialization; condition; update) {
    // body
}

// Print 1 to 10
for (int i = 1; i <= 10; i++) {
    cout << i << " ";
}
// Output: 1 2 3 4 5 6 7 8 9 10
```

### Range-based `for` (C++11)
```cpp
int arr[] = {10, 20, 30, 40};
for (int x : arr) {
    cout << x << " ";
}
// Output: 10 20 30 40
```

---

## 2️⃣ `while` Loop

Use when the **condition is checked before** each iteration.

```cpp
// Reverse a number
int num = 12345, rev = 0;
while (num > 0) {
    rev = rev * 10 + num % 10;
    num /= 10;
}
cout << rev;  // 54321
```

---

## 3️⃣ `do-while` Loop

Executes the body **at least once**, then checks the condition.

```cpp
int i = 1;
do {
    cout << i << " ";
    i++;
} while (i <= 5);
// Output: 1 2 3 4 5
```

> Even if `i = 10` at start, it still prints `10` once.

---

## Loop Comparison

| Loop | Condition Check | Min Executions | Best For |
|---|---|---|---|
| `for` | Before | 0 | Known number of iterations |
| `while` | Before | 0 | Unknown iterations, condition-based |
| `do-while` | After | 1 | Must execute at least once (menus, I/O) |

---

## 🦘 Jump Statements

### `break` — Exit the loop immediately
```cpp
for (int i = 1; i <= 10; i++) {
    if (i == 5) break;
    cout << i << " ";
}
// Output: 1 2 3 4
```

### `continue` — Skip current iteration
```cpp
for (int i = 1; i <= 10; i++) {
    if (i % 2 == 0) continue;
    cout << i << " ";
}
// Output: 1 3 5 7 9
```

### `goto` — Jump to a label (rare, avoid)
```cpp
int i = 1;
loop:
    cout << i << " ";
    i++;
    if (i <= 5) goto loop;
// Output: 1 2 3 4 5
```

---

## 🌀 Nested Loops — Patterns

```cpp
// Right triangle of stars
int rows = 5;
for (int i = 1; i <= rows; i++) {
    for (int j = 1; j <= i; j++)
        cout << "* ";
    cout << endl;
}
// Output:
// *
// * *
// * * *
// * * * *
// * * * * *
```

---

## ✅ Practice Tasks
1. Print the multiplication table of a given number using a `for` loop.
2. Find the sum of digits of a number using a `while` loop.
3. Print all prime numbers from 1 to 100.
4. Print the following pattern (use nested loops):
   ```
   1
   1 2
   1 2 3
   1 2 3 4
   ```
5. Find the factorial of a number using a loop.

---

## 📌 GFG Resources
- [Loops in C++](https://www.geeksforgeeks.org/cpp/cpp-loops/)
- [Break Statement](https://www.geeksforgeeks.org/cpp/decision-making-c-cpp/#brk)
- [Continue Statement](https://www.geeksforgeeks.org/cpp/decision-making-c-cpp/#cont)