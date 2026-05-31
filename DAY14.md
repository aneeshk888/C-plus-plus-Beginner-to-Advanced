
```markdown
# Day 14 - Dynamic Memory & malloc vs new

## Concepts
- `malloc`/`free` in C
- `new`/`delete` in C++
- Memory leaks and smart pointers

## Code Example
```cpp
int* arr = new int[5];
for(int i=0; i<5; i++) arr[i] = i;
delete[] arr;
