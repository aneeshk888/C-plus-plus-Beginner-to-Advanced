
---

#### `Day19-Multithreading/README.md`
```markdown
# Day 19 - Multithreading

## Concepts
- `std::thread`
- Joining and detaching threads
- Synchronization with mutex

## Code Example
```cpp
#include <thread>
void task() { cout << "Thread running\n"; }
int main() {
    thread t(task);
    t.join();
}
