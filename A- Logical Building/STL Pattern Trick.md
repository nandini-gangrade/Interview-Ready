
# 🧠 C++ STL TRICK CHART (WITH EXAMPLES + CODE + OUTPUT)

---

## 🔹 TRICK CHART: “WORDS → STL → CODE”

| Problem Words / Situation     | Use This STL          | Why                |
| ----------------------------- | --------------------- | ------------------ |
| count, frequency, occurrences | `unordered_map`       | Fast key → count   |
| already seen?, exists?        | `unordered_set`       | O(1) lookup        |
| remove duplicates             | `set`                 | Auto-unique        |
| sorted + unique               | `set`                 | Tree-based sorted  |
| sorted + duplicates           | `multiset`            | Allows repeats     |
| key → value                   | `map / unordered_map` | Mapping            |
| last in first out             | `stack`               | LIFO               |
| first in first out            | `queue`               | FIFO               |
| sliding window                | `deque`               | Push/pop both ends |
| largest / smallest            | `priority_queue`      | Heap               |
| all arrangements              | `next_permutation`    | Permutations       |
| binary / set bits             | `__builtin_popcount`  | Bit count          |

---

# ✅ 1. FREQUENCY COUNT

### 🗣️ Keywords

> count, frequency, occurrences

### ✅ STL

`unordered_map`

### 📌 Example

Input array: `1 2 2 3 1`

### 💻 Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    vector<int> arr = {1,2,2,3,1};
    unordered_map<int,int> freq;

    for(int x : arr)
        freq[x]++;

    for(auto it : freq)
        cout << it.first << " -> " << it.second << endl;
}
```

### 🖨️ Output (order may vary)

```
3 -> 1
2 -> 2
1 -> 2
```

### 🧠 Why it works?

* Keys = numbers
* Values = count
* Hashing makes it fast

---

# ✅ 2. CHECK IF ELEMENT EXISTS

### 🗣️ Keywords

> exists, already present, seen before

### ✅ STL

`unordered_set`

### 💻 Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    unordered_set<int> s = {1, 2, 3};

    if(s.count(2))
        cout << "Found";
    else
        cout << "Not Found";
}
```

### 🖨️ Output

```
Found
```

### 🧠 Why?

* `count(x)` returns 1 if exists
* No duplicates allowed

---

# ✅ 3. REMOVE DUPLICATES

### 🗣️ Keywords

> unique elements, remove duplicates

### ✅ STL

`set`

### 💻 Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    vector<int> arr = {1,2,2,3,1};

    set<int> s(arr.begin(), arr.end());

    for(int x : s)
        cout << x << " ";
}
```

### 🖨️ Output

```
1 2 3
```

### 🧠 Why?

* Set automatically removes duplicates
* Keeps elements sorted

---

# ✅ 4. SORTED + DUPLICATES ALLOWED

### 🗣️ Keywords

> sorted, duplicates allowed

### ✅ STL

`multiset`

### 💻 Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    multiset<int> ms;

    ms.insert(10);
    ms.insert(10);
    ms.insert(5);

    for(int x : ms)
        cout << x << " ";
}
```

### 🖨️ Output

```
5 10 10
```

### 🧠 Why?

* Multiset allows duplicates
* Maintains sorted order

---

# ✅ 5. KEY → VALUE MAPPING

### 🗣️ Keywords

> mapping, relation, dictionary

### ✅ STL

`map`

### 💻 Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    map<int,string> mp;

    mp[101] = "Aman";
    mp[102] = "Ravi";
    mp[100] = "Neha";

    for(auto it : mp)
        cout << it.first << " " << it.second << endl;
}
```

### 🖨️ Output

```
100 Neha
101 Aman
102 Ravi
```

### 🧠 Why?

* Map sorts by key automatically

---

# ✅ 6. FAST KEY → VALUE (MOST COMMON)

### 🗣️ Keywords

> frequency, fast lookup

### ✅ STL

`unordered_map`

### 💻 Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    unordered_map<char,int> mp;
    string s = "aabcc";

    for(char c : s)
        mp[c]++;

    for(auto it : mp)
        cout << it.first << " -> " << it.second << endl;
}
```

### 🖨️ Output (order may vary)

```
c -> 2
b -> 1
a -> 2
```

---

# ✅ 7. LAST IN FIRST OUT

### 🗣️ Keywords

> undo, back, reverse

### ✅ STL

`stack`

### 💻 Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    stack<int> st;

    st.push(10);
    st.push(20);
    st.push(30);

    cout << st.top() << endl;
    st.pop();
    cout << st.top();
}
```

### 🖨️ Output

```
30
20
```

### 🧠 Why?

* Stack removes last inserted element first

---

# ✅ 8. FIRST IN FIRST OUT

### 🗣️ Keywords

> queue, line, order

### ✅ STL

`queue`

### 💻 Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    queue<int> q;

    q.push(1);
    q.push(2);
    q.push(3);

    cout << q.front() << endl;
    q.pop();
    cout << q.front();
}
```

### 🖨️ Output

```
1
2
```

---

# ✅ 9. SLIDING WINDOW / BOTH ENDS

### 🗣️ Keywords

> window, subarray of size K

### ✅ STL

`deque`

### 💻 Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    deque<int> dq;

    dq.push_front(10);
    dq.push_back(20);
    dq.push_back(30);

    cout << dq.front() << " " << dq.back();
}
```

### 🖨️ Output

```
10 30
```

---

# ✅ 10. LARGEST / SMALLEST ELEMENT

### 🗣️ Keywords

> max, min, top K

### ✅ STL

`priority_queue`

### 💻 Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    priority_queue<int> pq;

    pq.push(10);
    pq.push(40);
    pq.push(20);

    cout << pq.top();
}
```

### 🖨️ Output

```
40
```

### 🧠 Why?

* Heap keeps maximum element on top

---

# ✅ 11. ALL PERMUTATIONS

### 🗣️ Keywords

> arrangements, permutations

### ✅ STL

`next_permutation`

### 💻 Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    string s = "123";

    do {
        cout << s << endl;
    } while(next_permutation(s.begin(), s.end()));
}
```

### 🖨️ Output

```
123
132
213
231
312
321
```

---

# ✅ 12. COUNT SET BITS

### 🗣️ Keywords

> binary, bits, set bits

### ✅ STL

`__builtin_popcount()`

### 💻 Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    cout << __builtin_popcount(13);
}
```

### 🖨️ Output

```
3
```

### 🧠 Why?

* 13 → `1101` → three 1s

---

# 🧠 FINAL ONE-LINE MEMORY TRICK

```
Count → unordered_map
Exist → unordered_set
Unique → set
Sorted + duplicate → multiset
Key-Value → map / unordered_map
Undo / Reverse → stack
Queue / Line → queue
Window → deque
Max / Min → priority_queue
Arrange → next_permutation
Bits → __builtin_popcount
```
