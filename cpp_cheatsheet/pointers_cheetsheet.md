# 🖇️ **C++ Pointers Cheat Sheet**

---

## 1️⃣ **Basic Syntax**

```cpp
int a = 10;
int* p = &a;   // p stores address of a
```

- `p` → pointer to int
- `*p` → value at address `p` ("dereference p")
- `&a` → address of variable `a`

---

## 2️⃣ **Declaring Pointers**

```cpp
int* p;    // pointer to int
double* q; // pointer to double
char* r;   // pointer to char
```

---

## 3️⃣ **Accessing Data via Pointer**

```cpp
int a = 5;
int* p = &a;
cout << *p;  // prints 5
```

---

## 4️⃣ **Changing Value through Pointer**

```cpp
*p = 10;  // now a == 10
```

---

## 5️⃣ **Pointer Arithmetic**

```cpp
int a[5] = {1,2,3,4,5};
int* p = a; // p points to a[0]

p++;  // points to a[1]
cout << *p; // prints 2

p += 2; // now points to a[3]
cout << *p; // prints 4
```

---

## 6️⃣ **Pointers and Arrays**

```cpp
int a[5] = {1,2,3,4,5};
int* p = a;

cout << *(p+2); // prints 3 (equivalent to a[2])
```

➡️ `a[i]` is equivalent to `*(a+i)`.

---

## 7️⃣ **Pointers to Pointers**

```cpp
int a = 5;
int* p = &a;
int** pp = &p;

cout << **pp; // prints 5
```

---

## 8️⃣ **Dynamic Memory Allocation**

### Allocate Memory

```cpp
int* p = new int;
*p = 10;
```

### Deallocate Memory

```cpp
delete p;
```

### Dynamic Array

```cpp
int* arr = new int[5]; // array of size 5
delete[] arr;         // free the array
```

---

## 9️⃣ **Function Parameters**

### Passing by Pointer

```cpp
void change(int* p) {
    *p = 100;
}

int a = 5;
change(&a); // a is now 100
```

---

## 10️⃣ **Const Pointers**

### Pointer to Constant Data

```cpp
const int* p = &a;
// *p cannot be changed; p can point elsewhere.
```

### Constant Pointer to Data

```cpp
int* const p = &a;
// p cannot point elsewhere; *p can be changed.
```

---

## 11️⃣ **Null Pointer**

```cpp
int* p = nullptr;
```

---

## 12️⃣ **Pointer vs Reference**

| Pointer                     | Reference                            |
| --------------------------- | ------------------------------------ |
| Can be `nullptr`            | Cannot be null                       |
| Can be reassigned           | Cannot be reassigned                 |
| Requires dereferencing `*p` | Automatically dereferenced           |
| Can point to dynamic memory | Typically used for parameter passing |

Example:

```cpp
int a = 10;
int& ref = a;  // Reference
int* p = &a;   // Pointer
```

---

## 13️⃣ **Common Mistakes**

✅ Forgetting `delete` → memory leak
✅ Dangling pointer → pointer to deleted object
✅ Dereferencing uninitialized/null pointer → crash
✅ Misunderstanding pointer arithmetic

---

## 14️⃣ **Usage in CP**

- Dynamic arrays for large sizes
- Fast passing of large arrays to functions
- Efficient graph representations (adjacency lists with pointers)
- DSU / Linked Lists
- Avoid if not required; **vector is safer** for containers.

---

# ⭐ Summary Diagram:

```cpp
int a = 10;
int* p = &a;      // p stores address of a
int** pp = &p;    // pp stores address of p

*a      → value at a
*p      → value at address p → a
**pp    → value at address p → a
```

---

If you want, I can also give:

✅ **Linked List (with pointer)** code
✅ **Graph adjacency list with pointer/vector**
✅ **Pointer tricks for CP**
✅ **Pointer-based recursion demo**

---

# 🧠 **Pointer-Based CP Patterns & Code Templates**

---

## 🔗 1️⃣ **Linked List Using Pointers**

```cpp
struct Node {
    int data;
    Node* next;

    Node(int val) {
        data = val;
        next = nullptr;
    }
};

void printList(Node* head) {
    while(head != nullptr) {
        cout << head->data << " ";
        head = head->next;
    }
}
```

**Use Case**: Fast insert/delete at head/tail/mid, custom memory control
**Time Complexities**:

- Insertion/Deletion: `O(1)` (at head), `O(n)` (at tail/mid)
- Search: `O(n)`

---

## 🌐 2️⃣ **Graph Using Adjacency List (Pointer Style)**

### Option 1: Vector of Vectors (Preferred)

```cpp
vector<vector<int>> adj(n);
adj[u].push_back(v);
adj[v].push_back(u); // for undirected graph
```

### Option 2: Vector of Pointers

```cpp
vector<int>* adj = new vector<int>[n];
adj[u].push_back(v);
```

**Don't forget** to `delete[] adj;` if using raw pointer.

---

## ⚔️ 3️⃣ **Disjoint Set Union (DSU / Union-Find)** with Path Compression

```cpp
int parent[100005];

int find(int x) {
    if(parent[x] == x) return x;
    return parent[x] = find(parent[x]); // path compression
}

void unite(int x, int y) {
    x = find(x);
    y = find(y);
    if(x != y) parent[x] = y;
}
```

**Use Case**: Connected components, Kruskal’s MST
**Time Complexity**:

- Find/Union: `O(α(n))` (inverse Ackermann) \~ constant

---

## 🔁 4️⃣ **Pointer-Based Recursion**

```cpp
void reversePrint(int* arr, int n) {
    if (n == 0) return;
    cout << arr[n-1] << " ";
    reversePrint(arr, n-1);
}
```

Or:

```cpp
void printForward(int* ptr, int* end) {
    if (ptr == end) return;
    cout << *ptr << " ";
    printForward(ptr + 1, end);
}
```

---

## 🧠 5️⃣ **Pointer Tricks in CP**

### a. Swap Without Temp

```cpp
void swap(int* a, int* b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}
```

### b. Multiple Return Values

```cpp
void compute(int a, int b, int* sum, int* product) {
    *sum = a + b;
    *product = a * b;
}
```

---

## 🚫 6️⃣ **Common Pointer Mistakes in CP**

| Mistake                               | What to Do                             |
| ------------------------------------- | -------------------------------------- |
| Dereferencing null/uninitialized      | Always initialize                      |
| Memory leaks                          | `delete` when using `new`              |
| Invalid memory access (out of bounds) | Always bounds check                    |
| Misuse in recursion                   | Use global or static storage if needed |

---

## 🏁 7️⃣ **Memory Management Template**

```cpp
int* arr = new int[n];   // dynamic array
// use arr
delete[] arr;            // free memory
```

✅ Use `std::vector` unless raw memory control is necessary.

---

## 📦 BONUS: Smart Pointers (C++11+)

If you're doing **advanced CP** or working in **interviews**:

```cpp
#include <memory>

shared_ptr<Node> ptr1 = make_shared<Node>(val);
unique_ptr<Node> ptr2 = make_unique<Node>(val);
```

✔️ Automatically manages memory
✔️ Safer than raw pointers
❌ Rarely needed in CP unless dealing with custom structures or trees

---

# ✅ Summary

| Task                   | Pointer Role                      |
| ---------------------- | --------------------------------- |
| Dynamic array          | `new` and `delete[]`              |
| Linked list            | `Node*` to manage nodes           |
| Graph adjacency list   | Array of vectors or vector\*      |
| DSU                    | `parent[]` as pointers to leaders |
| Swap, multiple returns | Use `*param` in function          |
| Memory optimization    | Reuse buffers using pointers      |

---

Let me know if you'd like:

📚 Visual diagrams for pointer memory layouts
🎯 Practice problems to master pointers in CP
🧪 Pointer debugging tips with `gdb` or IDEs
⚙️ How to build your own STL-like containers with pointers

Just say the word — and I’ll prep it 🚀
