

```markdown
# Day 12 - Polymorphism, Abstraction & Encapsulation

## Concepts
- Compile-time vs runtime polymorphism
- Abstract classes and pure virtual functions
- Encapsulation with getters/setters

## Code Example
```cpp
class Animal {
public:
    virtual void sound() = 0; // abstraction
};

class Dog : public Animal {
public:
    void sound() override { cout << "Woof!\n"; }
};
