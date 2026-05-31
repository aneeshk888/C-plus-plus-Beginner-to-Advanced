
---

#### `Day17-Exception-Handling/README.md`
```markdown
# Day 17 - Exception Handling

## Concepts
- `try`, `catch`, `throw`
- Standard exceptions
- Custom exceptions

## Code Example
```cpp
try {
    throw runtime_error("Error occurred");
} catch (exception& e) {
    cout << e.what();
}
