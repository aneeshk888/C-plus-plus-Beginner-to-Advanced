# 📘 Day 6 — Arrays in C++

> **GFG Curriculum Reference:** Day 6-8 (Part 1)

---

## 🔍 What is an Array?

An array stores **multiple elements of the same type** in contiguous memory. Access is done via **0-based index**.

---

## 📦 Declaration & Initialization

```cpp
// Declaration
int arr[5];                         // 5 integers, uninitialized

// Declaration + Initialization
int arr[5] = {10, 20, 30, 40, 50};

// Size inferred from initializer
int arr[] = {1, 2, 3, 4, 5};       // size = 5

// Partial initialization (rest are 0)
int arr[5] = {1, 2};               // {1, 2, 0, 0, 0}

// All zeros
int arr[5] = {0};
```

---

## 🔁 Traversal

```cpp
int arr[] = {10, 20, 30, 40, 50};
int n = sizeof(arr) / sizeof(arr[0]);  // n = 5

for (int i = 0; i < n; i++)
    cout << arr[i] << " ";
// Output: 10 20 30 40 50
```

---

## 📐 2D Arrays (Matrices)

```cpp
int mat[3][3] = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};

// Traversal
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 3; j++)
        cout << mat[i][j] << " ";
    cout << endl;
}
```

---

## 📥 Passing Arrays to Functions

Arrays **decay to pointers** when passed to functions — the original array is modified.

```cpp
void printArray(int arr[], int n) {
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
}

void reverseArray(int arr[], int n) {
    int l = 0, r = n - 1;
    while (l < r) {
        swap(arr[l], arr[r]);
        l++; r--;
    }
}

int main() {
    int a[] = {1, 2, 3, 4, 5};
    printArray(a, 5);   // 1 2 3 4 5
    reverseArray(a, 5);
    printArray(a, 5);   // 5 4 3 2 1
}
```

---

## 🧮 Common Array Operations

### Find Max & Min
```cpp
int arr[] = {3, 1, 7, 2, 9};
int n = 5;
int maxVal = arr[0], minVal = arr[0];
for (int i = 1; i < n; i++) {
    if (arr[i] > maxVal) maxVal = arr[i];
    if (arr[i] < minVal) minVal = arr[i];
}
// max = 9, min = 1
```

### Linear Search
```cpp
int search(int arr[], int n, int key) {
    for (int i = 0; i < n; i++)
        if (arr[i] == key) return i;
    return -1;  // not found
}
```

### Matrix Addition
```cpp
int a[2][2] = {{1,2},{3,4}};
int b[2][2] = {{5,6},{7,8}};
int c[2][2];

for (int i = 0; i < 2; i++)
    for (int j = 0; j < 2; j++)
        c[i][j] = a[i][j] + b[i][j];
```

---

## 💡 Key Notes

- Arrays are **fixed size** — size must be known at compile time (for static arrays).
- Accessing outside bounds (`arr[10]` on a size-5 array) causes **undefined behavior**.
- `sizeof(arr) / sizeof(arr[0])` gives the number of elements.
- For **dynamic-size arrays**, use `vector` from STL.

---

## ✅ Practice Tasks
1. Find the second largest element in an array.
2. Rotate an array to the left by K positions.
3. Count the frequency of each element in an array.
4. Check if an array is sorted in ascending order.
5. Transpose a 3×3 matrix.

---

## 📌 GFG Resources
- [Arrays in C++](https://www.geeksforgeeks.org/cpp/cpp-arrays/)
- [Multidimensional Arrays](https://www.geeksforgeeks.org/cpp/multidimensional-arrays-c-cpp/)