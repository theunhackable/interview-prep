Here’s a **complete C++ Data Structures + Time Complexities + Basic Methods cheat sheet** — perfect for **competitive programming**:

---

# 📚 C++ Data Structures Cheat Sheet

### With **Basic Methods** + **Time Complexities**

---

### 📌 1️⃣ **Array**

```cpp
int a[100];
```

- Access: `O(1)`
- Update: `O(1)`
- No built-in dynamic resizing → use vector instead.

---

### 📌 2️⃣ **Vector**

```cpp
vector<int> v;
```

**Common Methods**

```cpp
v.push_back(x);           // O(1) amortized
v.pop_back();             // O(1)
v.size();                 // O(1)
v.clear();                // O(n)
v[i];                     // O(1)
v.begin(), v.end();       // Iterators
sort(v.begin(), v.end()); // O(n log n)
reverse(v.begin(), v.end()); // O(n)
```

**Time Complexity**

- Access: `O(1)`
- Insert at end: `O(1)` (amortized)
- Insert/delete at middle: `O(n)`

---

### 📌 3️⃣ **Pair**

```cpp
pair<int, int> p = {x, y};
```

**Access**

```cpp
p.first;
p.second;
```

**Time Complexity**

- Access: `O(1)`

---

### 📌 4️⃣ **Set (Balanced BST - Red Black Tree)**

```cpp
set<int> s;
```

**Common Methods**

```cpp
s.insert(x);    // O(log n)
s.erase(x);     // O(log n)
s.count(x);     // O(log n)
s.find(x);      // O(log n), returns iterator
s.lower_bound(x); // O(log n)
s.upper_bound(x); // O(log n)
```

**Time Complexity**

- Insert: `O(log n)`
- Delete: `O(log n)`
- Search: `O(log n)`

---

### 📌 5️⃣ **Unordered Set (Hash Table)**

```cpp
unordered_set<int> us;
```

**Common Methods**

```cpp
us.insert(x);    // O(1) avg
us.erase(x);     // O(1) avg
us.count(x);     // O(1) avg
us.find(x);      // O(1) avg
```

**Time Complexity**

- Insert: `O(1)` average
- Delete: `O(1)` average
- Search: `O(1)` average

👉 **Worst-case: `O(n)` due to collisions** (rare)

---

### 📌 6️⃣ **Map (Balanced BST - Red Black Tree)**

```cpp
map<int, int> m;
```

**Common Methods**

```cpp
m[key] = value;    // O(log n)
m.erase(key);      // O(log n)
m.count(key);      // O(log n)
m.find(key);       // O(log n)
m.lower_bound(key); // O(log n)
m.upper_bound(key); // O(log n)
```

**Time Complexity**

- Insert: `O(log n)`
- Delete: `O(log n)`
- Search: `O(log n)`

---

### 📌 7️⃣ **Unordered Map (Hash Table)**

```cpp
unordered_map<int, int> um;
```

**Common Methods**

```cpp
um[key] = value;    // O(1) avg
um.erase(key);      // O(1) avg
um.count(key);      // O(1) avg
um.find(key);       // O(1) avg
```

**Time Complexity**

- Insert: `O(1)` average
- Delete: `O(1)` average
- Search: `O(1)` average

👉 **Worst-case: O(n)** (rare)

---

### 📌 8️⃣ **Stack (LIFO)**

```cpp
stack<int> st;
```

**Common Methods**

```cpp
st.push(x);      // O(1)
st.pop();        // O(1)
st.top();        // O(1)
st.empty();      // O(1)
st.size();       // O(1)
```

**Time Complexity**

- Push: `O(1)`
- Pop: `O(1)`
- Top: `O(1)`

---

### 📌 9️⃣ **Queue (FIFO)**

```cpp
queue<int> q;
```

**Common Methods**

```cpp
q.push(x);      // O(1)
q.pop();        // O(1)
q.front();      // O(1)
q.back();       // O(1)
q.empty();      // O(1)
```

**Time Complexity**

- Push: `O(1)`
- Pop: `O(1)`
- Front/Back: `O(1)`

---

### 📌 10️⃣ **Deque (Double-ended queue)**

```cpp
deque<int> dq;
```

**Common Methods**

```cpp
dq.push_back(x);     // O(1)
dq.push_front(x);    // O(1)
dq.pop_back();       // O(1)
dq.pop_front();      // O(1)
dq.front();          // O(1)
dq.back();           // O(1)
```

**Time Complexity**

- Push/pop front/back: `O(1)`

---

### 📌 11️⃣ **Priority Queue (Heap)**

**Max-Heap**

```cpp
priority_queue<int> pq;
```

**Min-Heap**

```cpp
priority_queue<int, vector<int>, greater<int>> pq;
```

**Common Methods**

```cpp
pq.push(x);      // O(log n)
pq.pop();        // O(log n)
pq.top();        // O(1)
pq.empty();      // O(1)
```

**Time Complexity**

- Push: `O(log n)`
- Pop: `O(log n)`
- Top: `O(1)`

---

### 📌 12️⃣ **Bitset**

```cpp
bitset<10> b;
```

**Common Methods**

```cpp
b.set(pos);    // O(1)
b.reset(pos);  // O(1)
b.flip(pos);   // O(1)
b.count();     // O(n)
b.test(pos);   // O(1)
```

**Time Complexity**

- Most operations: `O(1)`
- Count: `O(n)`

---

# ⭐ Summary Table

| Data Structure | Insert   | Delete   | Search   | Access |
| -------------- | -------- | -------- | -------- | ------ |
| Array          | O(1)     | O(n)     | O(n)     | O(1)   |
| Vector         | O(1)\*   | O(1)\*   | O(n)     | O(1)   |
| Set            | O(log n) | O(log n) | O(log n) | O(1)   |
| Unordered Set  | O(1)\*   | O(1)\*   | O(1)\*   | O(1)   |
| Map            | O(log n) | O(log n) | O(log n) | O(1)   |
| Unordered Map  | O(1)\*   | O(1)\*   | O(1)\*   | O(1)   |
| Stack          | O(1)     | O(1)     | O(1)     | O(1)   |
| Queue          | O(1)     | O(1)     | O(1)     | O(1)   |
| Deque          | O(1)     | O(1)     | O(1)     | O(1)   |
| Priority Queue | O(log n) | O(log n) | O(log n) | O(1)   |
| Bitset         | O(1)     | O(1)     | O(1)     | O(1)   |

\* Amortized \* Unordered containers may degrade to `O(n)` in worst-case.

_What is meant by amortized complexity?_
Amortized complexity is a way of analyzing the performance of algorithms or data structures that have occasional high-cost operations. It takes into account not only the worst-case scenario but also the average cost over a series of operations.16 Jun 2022

---
