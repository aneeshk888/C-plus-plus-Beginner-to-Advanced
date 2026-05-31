# Day 11 - Inheritance

## Concepts
- Types of inheritance (single, multiple, multilevel, hierarchical, hybrid)
- Access specifiers and their effect
- Function overriding

## Code Example
```cpp
class Base {
public:
    void greet() { cout << "Hello from Base\n"; }
};

class Derived : public Base {
public:
    void greet() { cout << "Hello from Derived\n"; }
};
