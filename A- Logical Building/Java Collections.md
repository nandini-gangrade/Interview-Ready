# 🚀 JAVA COLLECTIONS FRAMEWORK – COMPLETE BEGINNER → INTERVIEW GUIDE

---

## 1️⃣ What is a Framework? (Very Basic)

A **framework** is:

> a **set of rules + ready-made components** that help you solve common problems easily.

👉 Java Collections Framework (JCF) =
**ready-made data structures + common operations**, all designed to work together.

---

## 2️⃣ Why Collections? Why Not Arrays?

### Problem with Arrays

```java
int[] arr = new int[3];
```

❌ Fixed size
❌ No add/remove methods
❌ No built-in sorting/searching
❌ Error-prone

### Solution → Collections

✔ Dynamic size
✔ Rich APIs
✔ Clean, readable code
✔ Optimized internally

---

## 3️⃣ IMPORTANT JARGONS (MUST UNDERSTAND)

### 🔹 Iterable (interface)

**What it is:**
Anything that can be looped using `for-each`

```java
for(int x : collection)
```

**Why it exists:**
To allow uniform looping

---

### 🔹 Interface (VERY IMPORTANT)

An **interface**:

* Defines **what** methods exist
* Does NOT define **how** they work

Example:

```java
List list = new ArrayList();
```

👉 Code depends on **List**, not ArrayList
👉 Easy to change implementation later

---

### 🔹 Collection (interface)

Represents a **group of objects**

Common methods:

```java
add(), remove(), size(), clear(), contains()
```

---

## 4️⃣ BIG HIERARCHY (MEMORIZE THIS)

```
Iterable
   ↓
Collection
 ├── List
 ├── Set
 └── Queue
Map (separate but part of framework)
```

---

# 📦 LIST FAMILY (ORDERED + DUPLICATES)

---

## 5️⃣ List – What It Is

**List**:

* Ordered collection
* Allows duplicates
* Index based

### Real-life

👉 Playlist
👉 Student marks list

---

## 6️⃣ ArrayList

### What it is

* Dynamic array

### Why we need it

* Fast access using index

### When to use

* Read-heavy operations

### Internal working

* Uses array
* When full → new bigger array → copy

---

### Code

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        List<Integer> list = new ArrayList<>();
        list.add(10);
        list.add(20);
        list.add(10);

        System.out.println(list);
    }
}
```

### Output

```
[10, 20, 10]
```

### Why?

* Order preserved
* Duplicates allowed

---

## 7️⃣ Vector (LEGACY BUT IMPORTANT)

### What it is

* Old version of ArrayList
* **Synchronized (thread-safe)**

### Why exists

* For multi-threading (old Java)

### When to use

* Rarely (mostly exam theory)

### Internal

* Same as ArrayList but slower

---

### Code

```java
Vector<Integer> v = new Vector<>();
v.add(1);
v.add(2);
System.out.println(v);
```

### Output

```
[1, 2]
```

---

## 8️⃣ Stack (LEGACY – EXTENDS Vector)

### What it is

* LIFO (Last In First Out)

### Real-life

👉 Undo
👉 Browser back button

### Internal

* Uses Vector methods

---

### Code

```java
Stack<Integer> st = new Stack<>();
st.push(10);
st.push(20);

System.out.println(st.pop());
System.out.println(st.peek());
```

### Output

```
20
10
```

### Why?

* Last inserted removed first

👉 **TRICK:** Prefer `Deque` over Stack in real code

---

# 📦 SET FAMILY (UNIQUE ELEMENTS)

---

## 9️⃣ Set – What It Is

* No duplicates
* Order depends on implementation

### Real-life

👉 Unique usernames

---

## 🔟 HashSet

### What it is

* Hash table based

### When to use

* Fast lookup
* Order not required

---

### Code

```java
Set<Integer> set = new HashSet<>();
set.add(10);
set.add(5);
set.add(10);

System.out.println(set);
```

### Output (may vary)

```
[5, 10]
```

---

## 1️⃣1️⃣ SortedSet (INTERFACE)

### What it is

* Set with **sorted order**

### Why exists

* To enforce ordering

---

## 1️⃣2️⃣ NavigableSet (INTERFACE)

### What it is

* Extension of SortedSet
* Can **navigate elements**

Methods:

```java
lower(), higher(), floor(), ceiling()
```

---

## 1️⃣3️⃣ TreeSet

### What it is

* Implements NavigableSet
* Sorted + unique

### Internal

* Red-Black Tree

---

### Code

```java
TreeSet<Integer> ts = new TreeSet<>();
ts.add(20);
ts.add(10);
ts.add(30);

System.out.println(ts);
System.out.println(ts.lower(20));
```

### Output

```
[10, 20, 30]
10
```

### Why?

* Sorted automatically
* `lower(20)` → just smaller element

---

# 📦 QUEUE / DEQUE FAMILY

---

## 1️⃣4️⃣ Queue (INTERFACE)

### What it is

* FIFO (First In First Out)

### Real-life

👉 Line at bank

Methods:

```java
offer(), poll(), peek()
```

---

## 1️⃣5️⃣ PriorityQueue

### What it is

* Heap-based queue
* Highest (or lowest) priority first

### Internal

* Binary heap

---

### Code

```java
PriorityQueue<Integer> pq = new PriorityQueue<>();
pq.add(30);
pq.add(10);
pq.add(20);

System.out.println(pq.poll());
```

### Output

```
10
```

### Why?

* Min-heap by default

---

## 1️⃣6️⃣ Deque (DOUBLE ENDED QUEUE)

### What it is

* Insert/remove from both ends

### Real-life

👉 Sliding window problems

---

## 1️⃣7️⃣ ArrayDeque (MOST RECOMMENDED)

### What it is

* Resizable array
* Faster than Stack & LinkedList

---

### Code

```java
ArrayDeque<Integer> dq = new ArrayDeque<>();
dq.addFirst(10);
dq.addLast(20);

System.out.println(dq);
```

### Output

```
[10, 20]
```

---

# 📦 MAP FAMILY (KEY → VALUE)

---

## 1️⃣8️⃣ Map – What It Is

* Key-value pairs
* Keys unique

---

## 1️⃣9️⃣ HashMap

### Use

* Frequency counting
* Fast lookup

---

### Code

```java
HashMap<String,Integer> map = new HashMap<>();
map.put("apple", 1);
map.put("apple", 2);

System.out.println(map);
```

### Output

```
{apple=2}
```

---

## 2️⃣0️⃣ LinkedHashMap

* Maintains insertion order
* Used in LRU cache

---

## 2️⃣1️⃣ TreeMap

* Sorted keys
* Red-Black Tree

---

# 🧠 COLLECTIONS UTILITY CLASS

```java
Collections.sort(list);
Collections.reverse(list);
Collections.shuffle(list);
```

---

# 🎯 FINAL SUPER TRICK CHART (MEMORIZE THIS)

## 🔥 WORD → COLLECTION

| Problem Words         | Use           |
| --------------------- | ------------- |
| ordered + duplicates  | ArrayList     |
| thread-safe list      | Vector        |
| undo / LIFO           | Stack / Deque |
| unique                | HashSet       |
| sorted unique         | TreeSet       |
| just smaller / larger | NavigableSet  |
| FIFO                  | Queue         |
| priority              | PriorityQueue |
| window                | ArrayDeque    |
| key-value             | HashMap       |
| sorted keys           | TreeMap       |

---

## 🧠 ONE-LINE MEMORY SPELL

```
ArrayList → read fast
LinkedList → insert fast
Vector/Stack → legacy
HashSet → unique fast
TreeSet → unique sorted
Queue → FIFO
PriorityQueue → heap
Deque → window / stack
HashMap → frequency
TreeMap → sorted keys
```
