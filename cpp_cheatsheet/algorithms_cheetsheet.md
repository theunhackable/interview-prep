---

# 🎯 **1️⃣ Common Use Cases of Each Data Structure**

| Data Structure | Typical Use Cases                                           |
| -------------- | ----------------------------------------------------------- |
| Array          | Static data, indexing, fast iteration                       |
| Vector         | Dynamic array, fast end insertions, storing lists           |
| Pair           | Storing related values (coordinates, weight-index pairs)    |
| Set            | Storing unique sorted values, fast lookup                   |
| Unordered Set  | Storing unique values, fast lookup, no order                |
| Map            | Key-value pairs with sorted keys, ordered maps              |
| Unordered Map  | Key-value pairs with fast access, hash-based                |
| Stack          | Expression evaluation, undo operations, recursion emulation |
| Queue          | BFS traversal, order-preserving processing                  |
| Deque          | Sliding window problems, fast insert/remove from both ends  |
| Priority Queue | Dijkstra’s algorithm, greedy problems, top-k problems       |
| Bitset         | Compact representation of bit arrays, subset generation     |

---

# 🛠️ **2️⃣ Common STL Algorithm Functions**

### 🔍 Binary Search

```cpp
bool found = binary_search(v.begin(), v.end(), x); // O(log n)
```

### 📍 Lower Bound (first element >= x)

```cpp
auto it = lower_bound(v.begin(), v.end(), x); // O(log n)
```

### 📍 Upper Bound (first element > x)

```cpp
auto it = upper_bound(v.begin(), v.end(), x); // O(log n)
```

### 🗂️ Next/Prev Permutation

```cpp
next_permutation(v.begin(), v.end()); // O(n)
prev_permutation(v.begin(), v.end()); // O(n)
```

### 🔀 Shuffle

```cpp
random_shuffle(v.begin(), v.end()); // O(n) — deprecated C++17
shuffle(v.begin(), v.end(), rng);   // use this with mt19937
```

### 🧮 Accumulate

```cpp
#include <numeric>
int sum = accumulate(v.begin(), v.end(), 0); // O(n)
```

### 🌟 Max/Min

```cpp
auto mx = *max_element(v.begin(), v.end()); // O(n)
auto mn = *min_element(v.begin(), v.end()); // O(n)
```

### Count Elements

```cpp
int cnt = count(v.begin(), v.end(), x); // O(n)
```

### Remove Elements

```cpp
v.erase(remove(v.begin(), v.end(), x), v.end()); // O(n)
```

---

# ⚠️ **3️⃣ Common Mistakes & Pitfalls in CP**

| Mistake                                          | Advice                                                            |
| ------------------------------------------------ | ----------------------------------------------------------------- |
| Using `unordered_map` with pairs                 | Requires custom hash, use `map` if unsure                         |
| Integer overflow (`int * int`)                   | Use `long long` when needed, `1LL * a * b`                        |
| Not using `ios::sync_with_stdio(false)`          | Slows down I/O, always enable fast I/O                            |
| Infinite loop in `while(cin >> x)`               | Check EOF handling carefully                                      |
| Not resetting visited\[] array in DFS/BFS        | Always reset between test cases                                   |
| Using `vector<int> a(n)` inside large recursion  | Causes stack overflow → declare globally or avoid large recursion |
| STL lower_bound/upper_bound assumes sorted input | Always sort before using                                          |
| Using `priority_queue` when needing min heap     | Use `greater<int>` template properly                              |
| Mixing `scanf/printf` with `cin/cout`            | Avoid this, causes sync issues                                    |
| Forgetting to modulo `MOD` at each step          | Always apply `MOD` where needed in formulae                       |
| Using `==` with floating point                   | NEVER do this — use `abs(a-b) < eps` with small epsilon           |

---

# ✅ Summary of Template to Start Any CP Problem

```cpp
#include <bits/stdc++.h>
using namespace std;
#define int long long
#define pb push_back
#define all(x) x.begin(), x.end()
const int MOD = 1e9+7;
const int INF = 1e18;

void solve() {
    // Read inputs
    // Write logic
    // Output answers
}

int32_t main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int t = 1;
    cin >> t;
    while(t--) {
        solve();
    }
    return 0;
}
```

---

# 🎁 Final Tips for CP

✅ Use `int` → `long long` in problems with large numbers
✅ Use **`priority_queue`** for greedy optimization
✅ **Precompute** things where possible → factorials, primes (Sieve), powers
✅ For **graph problems** → know BFS, DFS, Dijkstra, Union-Find
✅ For **DP** → tabulation preferred for speed; memoization for readability
✅ Keep your own **template.cpp** ready

---
