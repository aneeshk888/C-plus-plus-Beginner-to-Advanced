# 📘 Day 4 — Conditional Statements

> **GFG Curriculum Reference:** Day 4-5 (Part 1)

---

## 🔍 What are Decision-Making Statements?

Decision-making statements allow a program to **execute different code blocks** based on conditions, controlling the flow of execution.

---

## 1️⃣ `if` Statement

Executes a block only if the condition is **true**.

```cpp
int n = 10;
if (n > 0) {
    cout << "Positive number" << endl;
}
```

---

## 2️⃣ `if-else` Statement

```cpp
int age = 17;
if (age >= 18) {
    cout << "Eligible to vote";
} else {
    cout << "Not eligible to vote";
}
// Output: Not eligible to vote
```

---

## 3️⃣ `else if` Ladder

```cpp
int marks = 75;
if (marks >= 90)
    cout << "Grade: A";
else if (marks >= 75)
    cout << "Grade: B";
else if (marks >= 60)
    cout << "Grade: C";
else
    cout << "Grade: F";
// Output: Grade: B
```

---

## 4️⃣ Nested `if-else`

```cpp
int x = 10, y = 20, z = 15;
if (x > y) {
    if (x > z) cout << "x is greatest";
    else        cout << "z is greatest";
} else {
    if (y > z) cout << "y is greatest";
    else        cout << "z is greatest";
}
// Output: y is greatest
```

---

## 5️⃣ `switch-case`

Used when you need to compare a variable against **multiple constant values**.

```cpp
int day = 3;
switch (day) {
    case 1: cout << "Monday";    break;
    case 2: cout << "Tuesday";   break;
    case 3: cout << "Wednesday"; break;
    case 4: cout << "Thursday";  break;
    case 5: cout << "Friday";    break;
    default: cout << "Weekend";
}
// Output: Wednesday
```

> ⚠️ Always use `break` — without it, **fall-through** executes the next case too!

### Fall-through Example (intentional)
```cpp
int month = 2;
switch (month) {
    case 1: case 3: case 5: case 7:
    case 8: case 10: case 12:
        cout << "31 days"; break;
    case 4: case 6: case 9: case 11:
        cout << "30 days"; break;
    case 2:
        cout << "28 or 29 days"; break;
}
```

---

## 6️⃣ Execute Both `if` and `else` (using goto — rare)

GFG covers this edge case: you can use `goto` to execute both branches in certain patterns, though it's rarely used in practice.

---

## 🧠 Short-Circuit Evaluation

```cpp
int a = 5;
// If first condition is false in &&, second is NOT evaluated
if (a > 10 && a++ > 0)
    cout << "True";
cout << a;  // still 5 — a++ was never reached
```

---

## ✅ Practice Tasks
1. Read a number and print if it is positive, negative, or zero.
2. Write a simple calculator using `switch-case` (+, -, *, /).
3. Given a year, check if it is a leap year using nested `if`.
4. Read a character and check if it is a vowel, consonant, digit, or special character.

---

## 📌 GFG Resources
- [Decision Making in C++](https://www.geeksforgeeks.org/cpp/decision-making-c-cpp/)
- [Switch Statement in C++](https://www.geeksforgeeks.org/cpp/switch-statement-in-cpp/)