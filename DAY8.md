# 📘 Day 8 — Pointers, Namespaces & Wild Pointers

> **GFG Curriculum Reference:** Day 6-8 (Part 3)

---

## 🔍 What is a Pointer?

A pointer is a variable that **stores the memory address** of another variable.

```
Variable:   int x = 10;
Memory:     [address 1000] → value 10

Pointer:    int *ptr = &x;
ptr stores: 1000 (address of x)
*ptr gives: 10   (value at that address)
```

---

## 📌 Basic Pointer Syntax

```cpp
int x = 10;
int *ptr = &x;          // ptr holds address of x

cout << x    << endl;   // 10       — value of x
cout << &x   << endl;   // 0x...    — address of x
cout << ptr  << endl;   // 0x...    — same address (ptr stores it)
cout << *ptr << endl;   // 10       — dereference: value AT the address

*ptr = 50;              // modify x through pointer
cout << x << endl;      // 50
```

---

## ➕ Pointer Arithmetic

Pointers can be incremented/decremented — they move by the **size of the data type**.

```cpp
int arr[] = {10, 20, 30, 40, 50};
int *p = arr;           // p points to arr[0]

cout << *p       << endl;  // 10
cout << *(p + 1) << endl;  // 20
cout << *(p + 2) << endl;  // 30

p++;                       // now points to arr[1]
cout << *p << endl;        // 20
```

---

## 🔡 Pointer to Pointer

```cpp
int val = 100;
int *p   = &val;
int **pp = &p;

cout << val  << endl;  // 100
cout << *p   << endl;  // 100
cout << **pp << endl;  // 100
```

---

## 🆕 Dynamic Memory Allocation

```cpp
// Single variable
int *ptr = new int(25);
cout << *ptr << endl;   // 25
delete ptr;             // free memory
ptr = nullptr;          // good practice

// Dynamic array
int n = 5;
int *arr = new int[n];
for (int i = 0; i < n; i++) arr[i] = i * 10;
delete[] arr;           // must use delete[] for arrays
```

---

## ⚖️ Pointers vs References

| Feature | Pointer (`*`) | Reference (`&`) |
|---|---|---|
| Null value | ✅ `nullptr` allowed | ❌ Must refer to a variable |
| Reassignable | ✅ Can point elsewhere | ❌ Fixed after initialization |
| Arithmetic | ✅ `ptr++` works | ❌ Not supported |
| Syntax | `int *p = &a` | `int &r = a` |
| Use case | Dynamic memory, arrays | Function parameters, aliases |

---

## 🌐 Namespaces

Namespaces prevent **name conflicts** when combining multiple libraries.

```cpp
namespace MyLib {
    int value = 42;
    void greet() { cout << "Hello from MyLib"; }
}

namespace OtherLib {
    int value = 99;
}

int main() {
    cout << MyLib::value   << endl;  // 42
    cout << OtherLib::value << endl; // 99
    MyLib::greet();
}
```

### `using` directive
```cpp
using namespace MyLib;
cout << value;   // 42 — no need for MyLib::
greet();
```

> **Why `using namespace std;`?** It lets you write `cout` instead of `std::cout`.

---

## ⚠️ Wild Pointers

A **wild pointer** is a pointer that is **not initialized** and points to some random memory.

```cpp
int *p;             // WILD pointer — dangerous!
*p = 10;            // Undefined behavior — could crash or corrupt memory
```

### How to avoid:
```cpp
int *p = nullptr;   // Safe null pointer
// OR
int x = 10;
int *p = &x;        // Initialize immediately
```

### Dangling Pointer (related)
```cpp
int *p = new int(5);
delete p;
// p is now a DANGLING pointer — still holds the old address
p = nullptr;        // Fix: set to nullptr after delete
```

---

## ✅ Practice Tasks
1. Swap two numbers using pointers.
2. Write a function that returns both min and max of an array using pointers.
3. Demonstrate pointer arithmetic on an integer array.
4. Create a dynamic 2D array using `new`, fill it, and then `delete` it.

---

## 📌 GFG Resources
- [Pointers in C++](https://www.geeksforgeeks.org/cpp/cpp-pointers/)
- [Pointers vs References](https://www.geeksforgeeks.org/cpp/pointers-vs-references-cpp/)
- [Namespaces in C++](https://www.geeksforgeeks.org/cpp/namespace-in-c/)
- [Wild Pointers](https://www.geeksforgeeks.org/dsa/what-are-wild-pointers-how-can-we-avoid/)