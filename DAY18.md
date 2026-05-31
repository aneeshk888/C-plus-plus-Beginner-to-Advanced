
---

#### `Day18-Signal-Handling/README.md`
```markdown
# Day 18 - Signal Handling

## Concepts
- Signals in C++
- `signal()` function
- Handling interrupts

## Code Example
```cpp
#include <csignal>
void handler(int signum) { cout << "Interrupt: " << signum; }
signal(SIGINT, handler);
