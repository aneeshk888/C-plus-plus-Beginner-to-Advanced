# 📘 Day 3 — Operators, References & Operator Overloading

> **GFG Curriculum Reference:** Day 2-3 (Part 2)

---

## 🔢 Types of Operators in C++

C++ operators are classified into **6 types**.

---

### 1. Arithmetic Operators

| Operator | Name | Example | Result |
|---|---|---|---|
| `+` | Addition | `8 + 3` | `11` |
| `-` | Subtraction | `8 - 3` | `5` |
| `*` | Multiplication | `8 * 3` | `24` |
| `/` | Division | `8 / 3` | `2` (integer division!) |
| `%` | Modulo | `8 % 3` | `2` |
| `++` | Increment | `++a` / `a++` | +1 |
| `--` | Decrement | `--a` / `a--` | -1 |

```cpp
int a = 8, b = 3;
cout << a + b << endl;   // 11
cout << a / b << endl;   // 2  ← integer division truncates
cout << ++a   << endl;   // 9  ← pre-increment: increment first, then use
cout << b--   << endl;   // 3  ← post-decrement: use first, then decrement
```

> ⚠️ `%` only works with integers. For float/double division, cast first: `(double)a / b`

---

### 2. Relational Operators

Used for comparison. Always return `true` (1) or `false` (0).

| Operator | Meaning |
|---|---|
| `==` | Equal to |
| `!=` | Not equal to |
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater than or equal |
| `<=` | Less than or equal |

```cpp
int x = 5, y = 10;
cout << (x == y) << endl;  // 0 (false)
cout << (x < y)  << endl;  // 1 (true)
```

---

### 3. Logical Operators

| Operator | Name | Description |
|---|---|---|
| `&&` | AND | True only if both are true |
| `\|\|` | OR | True if at least one is true |
| `!` | NOT | Inverts the boolean value |

```cpp
bool a = true, b = false;
cout << (a && b) << endl;  // 0
cout << (a || b) << endl;  // 1
cout << (!a)     << endl;  // 0
```

---

### 4. Bitwise Operators

Operate on binary representation of integers.

| Operator | Name | Example (`5=0101`, `3=0011`) |
|---|---|---|
| `&` | AND | `5 & 3 = 1` (0001) |
| `\|` | OR | `5 \| 3 = 7` (0111) |
| `^` | XOR | `5 ^ 3 = 6` (0110) |
| `~` | NOT | `~5 = -6` |
| `<<` | Left shift | `5 << 1 = 10` |
| `>>` | Right shift | `5 >> 1 = 2` |

---

### 5. Assignment Operators

```cpp
int a = 10;
a += 5;   // a = 15
a -= 3;   // a = 12
a *= 2;   // a = 24
a /= 4;   // a = 6
a %= 4;   // a = 2
```

### 6. Ternary Operator
```cpp
int x = 10, y = 20;
int max = (x > y) ? x : y;
cout << max;  // 20
```

---

## 🔗 Reference Variables

A reference is an **alias** for an existing variable — not a copy, not a pointer.

```cpp
int a = 10;
int &ref = a;   // ref IS a — same memory location

ref = 99;
cout << a;      // 99
```

> Key rules:
> - Must be **initialized** at declaration
> - Cannot be **reassigned** to refer to another variable
> - No null references

---

## 🔄 Operator Overloading

Allows you to redefine how operators work for your custom classes.

```cpp
class Point {
public:
    int x, y;
    Point(int x, int y) : x(x), y(y) {}

    // Overloading + operator
    Point operator+(const Point &p) {
        return Point(x + p.x, y + p.y);
    }
};

int main() {
    Point p1(1, 2), p2(3, 4);
    Point p3 = p1 + p2;
    cout << p3.x << ", " << p3.y;  // 4, 6
}
```

---

## ✅ Practice Tasks
1. Swap two numbers using XOR bitwise operator.
2. Check if a number is even using bitwise AND (`n & 1`).
3. Create a `Complex` class and overload `+` and `-` operators.
4. Use the ternary operator to find the largest of three numbers.

---

## 📌 GFG Resources
- [Operators in C++](https://www.geeksforgeeks.org/cpp/operators-in-cpp/)
- [Reference Variables](https://www.geeksforgeeks.org/cpp/references-in-cpp/)
- [Operator Overloading](https://www.geeksforgeeks.org/cpp/operator-overloading-cpp/)
- [Default Arguments](https://www.geeksforgeeks.org/cpp/default-arguments-c/)