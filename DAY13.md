
```markdown
# Day 13 - File Handling & I/O Streams

## Concepts
- `ifstream`, `ofstream`, `fstream`
- Reading/writing text files
- Error handling in file operations

## Code Example
```cpp
ofstream out("data.txt");
out << "Hello File!";
out.close();

ifstream in("data.txt");
string line;
getline(in, line);
cout << line;
