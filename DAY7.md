# 📘 Day 7 — Strings in C++

> **GFG Curriculum Reference:** Day 6-8 (Part 2)

---

## 🔍 Two Ways to Handle Strings

| | C-Style (`char[]`) | `std::string` |
|---|---|---|
| Header | none / `<cstring>` | `<string>` |
| Null-terminator | Manual `\0` | Automatic |
| Resize | Fixed | Dynamic |
| Functions | `strlen`, `strcpy`, `strcmp` | `.length()`, `+`, `==` |
| Prefer? | ❌ Low-level | ✅ Modern C++ |

---

## 1️⃣ C-Style Strings

```cpp
char name[] = "Alice";          // Automatically adds '\0'
char city[10] = "Delhi";

cout << name << endl;           // Alice
cout << strlen(name) << endl;   // 5

// Copy
char dest[20];
strcpy(dest, name);

// Concatenate
char full[30] = "Hello ";
strcat(full, name);
cout << full;                   // Hello Alice

// Compare
if (strcmp(name, "Alice") == 0)
    cout << "Same string";
```

---

## 2️⃣ `std::string` (Preferred)

```cpp
#include <string>
using namespace std;

string s = "Hello World";

// Length
cout << s.length() << endl;         // 11
cout << s.size()   << endl;         // 11 (same)

// Access characters
cout << s[0]       << endl;         // H
cout << s.at(6)    << endl;         // W

// Substring
cout << s.substr(6, 5) << endl;     // World

// Find
cout << s.find("World") << endl;    // 6
// Returns string::npos if not found

// Replace
s.replace(6, 5, "C++");
cout << s << endl;                   // Hello C++

// Append / Concatenate
string a = "Hello", b = " World";
string c = a + b;
cout << c << endl;                   // Hello World

// Compare
if (a == "Hello") cout << "Match";
```

---

## 🔄 String Algorithms

### Reverse
```cpp
#include <algorithm>
string s = "hello";
reverse(s.begin(), s.end());
cout << s;  // olleh
```

### Sort characters
```cpp
string s = "dcba";
sort(s.begin(), s.end());
cout << s;  // abcd
```

### Palindrome Check
```cpp
string s = "racecar";
string rev = s;
reverse(rev.begin(), rev.end());
if (s == rev) cout << "Palindrome";
```

### Count character frequency
```cpp
string s = "hello world";
int freq[26] = {0};
for (char c : s)
    if (c >= 'a' && c <= 'z')
        freq[c - 'a']++;
// freq[7] = freq['h'-'a'] = 1
```

---

## 📥 Reading Strings with Spaces

```cpp
string line;
getline(cin, line);     // reads entire line including spaces
cout << line;
```

> `cin >> s` stops at whitespace. Use `getline` for full lines.

---

## 🔤 Character Functions (`<cctype>`)

```cpp
#include <cctype>
char c = 'A';
isalpha(c);   // true — is letter
isdigit(c);   // false — is digit
isupper(c);   // true — is uppercase
islower(c);   // false
toupper('a'); // 'A'
tolower('A'); // 'a'
```

---

## ✅ Practice Tasks
1. Check if a string is a palindrome.
2. Count vowels and consonants in a string.
3. Check if two strings are anagrams.
4. Remove all spaces from a string.
5. Find the most frequent character in a string.

---

## 📌 GFG Resources
- [Strings in C++](https://www.geeksforgeeks.org/cpp/strings-in-cpp-and-how-to-create-them/)
- [std::string class](https://www.geeksforgeeks.org/cpp/stdstring-class-in-c/)