# 🚀 C++ STL COMPLETE HANDBOOK

*(Containers + Algorithms + Practice)*

---

## 🔹 What is C++ STL? (Beginner Intuition)

Imagine you are building a house.

* You **can** make every brick yourself (write data structures from scratch)
* OR you can use **ready-made bricks** (STL)

👉 **STL = Ready-made, optimized data structures + algorithms**

STL saves:

* Time ⏱️
* Code length ✂️
* Bugs 🐛

That’s why **competitive programmers LOVE STL**.

---

# 📦 PART 1: STL CONTAINERS (STEP-BY-STEP)

---

## 1️⃣ `vector` – Dynamic Array

### 🔹 What is vector?

* An array that can **grow or shrink**
* Stored in **continuous memory**
* Indexing is fast

### 🔹 When to use?

* When number of elements is unknown
* When you need fast access using index

### 🌍 Real-Life Example

👉 Store marks of students (students can increase later)

---

### ✅ Code (Type & Run)

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    vector<int> v;

    v.push_back(10);
    v.push_back(20);
    v.push_back(30);

    for(int i = 0; i < v.size(); i++) {
        cout << v[i] << " ";
    }
}
```

### 🖨️ Output

```
10 20 30
```

### 🧠 Why this output?

* `push_back()` adds elements at the end
* Loop prints elements using index
* `v.size()` = 3

---

## 2️⃣ `set` – Sorted + Unique

### 🔹 What is set?

* Stores **only unique values**
* Automatically **sorted**
* Uses balanced tree internally

### 🔹 When to use?

* Remove duplicates
* Need sorted data

### 🌍 Real-Life Example

👉 Unique roll numbers of students (sorted)

---

### ✅ Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    set<int> s;

    s.insert(5);
    s.insert(1);
    s.insert(5); // duplicate

    for(auto x : s)
        cout << x << " ";
}
```

### 🖨️ Output

```
1 5
```

### 🧠 Why?

* Duplicate `5` ignored
* Set keeps elements sorted

---

## 3️⃣ `unordered_set` – Fast Unique Lookup

### 🔹 What is unordered_set?

* Unique elements
* **No order**
* Uses hashing → very fast

### 🔹 When to use?

* Only care if element exists
* Order does NOT matter

### 🌍 Real-Life Example

👉 Check if username already exists

---

### ✅ Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    unordered_set<int> us;

    us.insert(10);
    us.insert(20);
    us.insert(10);

    for(auto x : us)
        cout << x << " ";
}
```

### 🖨️ Output (order may vary)

```
20 10
```

### 🧠 Why?

* Duplicate ignored
* Hash table does not maintain order

---

## 4️⃣ `multiset` – Sorted + Duplicates Allowed

### 🔹 When to use?

* Same value can appear multiple times
* Sorted order needed

### 🌍 Example

👉 Marks list where many students have same marks

---

### ✅ Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    multiset<int> ms;

    ms.insert(10);
    ms.insert(10);
    ms.insert(5);

    for(auto x : ms)
        cout << x << " ";
}
```

### 🖨️ Output

```
5 10 10
```

### 🧠 Why?

* Duplicates allowed
* Always sorted

---

## 5️⃣ `map` – Sorted Key → Value

### 🔹 What is map?

* Stores **key : value**
* Keys are unique
* Sorted by key

### 🔹 When to use?

* When order of keys matters

### 🌍 Real-Life Example

👉 Roll number → Student name

---

### ✅ Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    map<int, string> mp;

    mp[2] = "Mango";
    mp[1] = "Apple";
    mp[3] = "Banana";

    for(auto x : mp) {
        cout << x.first << " " << x.second << endl;
    }
}
```

### 🖨️ Output

```
1 Apple
2 Mango
3 Banana
```

### 🧠 Why?

* Map sorts by **key**
* Insertion order doesn’t matter

---

## 6️⃣ `unordered_map` ⭐ MOST IMPORTANT

### 🔹 What is unordered_map?

* Key → Value
* Fast (hashing)
* No order

### 🔹 When to use?

* Frequency counting
* Fast lookup problems

### 🌍 Real-Life Example

👉 Count votes / word frequency

---

### ✅ Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    unordered_map<string, int> freq;

    freq["apple"]++;
    freq["banana"]++;
    freq["apple"]++;

    for(auto x : freq) {
        cout << x.first << " -> " << x.second << endl;
    }
}
```

### 🖨️ Output (order may vary)

```
banana -> 1
apple -> 2
```

### 🧠 Why?

* `"apple"` inserted twice → count becomes 2
* Hash map does not maintain order

---

## 7️⃣ `stack` – LIFO (Last In First Out)

### 🔹 When to use?

* Undo / Redo
* Parenthesis checking

### 🌍 Example

👉 Browser back button

---

### ✅ Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    stack<int> st;

    st.push(10);
    st.push(20);

    cout << st.top() << endl;
    st.pop();
    cout << st.top();
}
```

### 🖨️ Output

```
20
10
```

### 🧠 Why?

* Last inserted element comes out first

---

## 8️⃣ `queue` – FIFO (First In First Out)

### 🌍 Example

👉 Line at ticket counter

---

### ✅ Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    queue<int> q;

    q.push(10);
    q.push(20);

    cout << q.front() << endl;
    q.pop();
    cout << q.front();
}
```

### 🖨️ Output

```
10
20
```

### 🧠 Why?

* First inserted element removed first

---

## 9️⃣ `deque` – Double Ended Queue

### 🔹 When to use?

* Sliding window problems

---

### ✅ Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    deque<int> dq;

    dq.push_front(10);
    dq.push_back(20);

    cout << dq.front() << " " << dq.back();
}
```

### 🖨️ Output

```
10 20
```

---

## 🔟 `priority_queue` – Heap

### 🔹 When to use?

* Always need maximum or minimum

---

### ✅ Code (Max Heap)

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    priority_queue<int> pq;

    pq.push(10);
    pq.push(30);
    pq.push(20);

    cout << pq.top();
}
```

### 🖨️ Output

```
30
```

### 🧠 Why?

* Priority queue keeps largest element on top

---

# ⚙️ PART 2: STL ALGORITHMS

---

## `sort()`

```cpp
vector<int> v = {3,1,2};
sort(v.begin(), v.end());
```

### Output

```
1 2 3
```

---

## `min_element()` & `max_element()`

```cpp
cout << *min_element(v.begin(), v.end());
cout << *max_element(v.begin(), v.end());
```

---

## `next_permutation()`

```cpp
string s = "123";
do {
    cout << s << endl;
} while(next_permutation(s.begin(), s.end()));
```

### Output

```
123
132
213
231
312
321
```

---

## `__builtin_popcount()`

```cpp
cout << __builtin_popcount(7);
```

### Output

```
3
```

### 🧠 Why?

* 7 → `111` (three 1s)

---

# 🧪 PART 3: PRACTICE PROBLEMS

### Problem 1: Remove Duplicates

👉 Use `set`

### Problem 2: Frequency Count

👉 Use `unordered_map`

### Problem 3: Balanced Parentheses

👉 Use `stack`

### Problem 4: K Largest Elements

👉 Use `priority_queue`

### Problem 5: Sliding Window Maximum

👉 Use `deque`

---

# 🎯 FINAL LEARNING ORDER (IMPORTANT)

1. vector
2. unordered_map
3. set
4. stack / queue
5. priority_queue
6. deque

Master these → **STL becomes automatic**

--
