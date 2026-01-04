# 🧠 JAVA COLLECTIONS – TRUE TRICK CHART

*(Situation → Collection → Code → Output → Reason)*

---

## 1️⃣ “count”, “frequency”, “number of times”, “occurrences”

### ✅ Use

**HashMap**

### 📌 Example

Count characters in `"aabcc"`

### 💻 Code

```java
HashMap<Character, Integer> map = new HashMap<>();
String s = "aabcc";

for (char c : s.toCharArray())
    map.put(c, map.getOrDefault(c, 0) + 1);

System.out.println(map);
```

### 🖨️ Output

```
{a=2, b=1, c=2}
```

### 🧠 Why it works

* Key = character
* Value = count
* HashMap gives **O(1)** average lookup

👉 **TRICK**: 90% “frequency” problems = `HashMap`

---

## 2️⃣ “exists?”, “already seen?”, “duplicate check?”

### ✅ Use

**HashSet**

### 📌 Example

Check if a number already appeared

### 💻 Code

```java
HashSet<Integer> set = new HashSet<>();

int x = 10;
if (set.contains(x))
    System.out.println("Duplicate");
else {
    set.add(x);
    System.out.println("First time");
}
```

### 🖨️ Output

```
First time
```

### 🧠 Why it works

* HashSet stores **only unique**
* `contains()` is fast

👉 **TRICK**: “seen before” = `HashSet`

---

## 3️⃣ “remove duplicates”

### ✅ Use

**HashSet** (unordered)
**LinkedHashSet** (keep order)

### 📌 Example

Remove duplicates but keep order

### 💻 Code

```java
List<Integer> list = Arrays.asList(1,2,2,3,1);
Set<Integer> set = new LinkedHashSet<>(list);

System.out.println(set);
```

### 🖨️ Output

```
[1, 2, 3]
```

### 🧠 Why it works

* Set removes duplicates
* LinkedHashSet preserves insertion order

---

## 4️⃣ “sorted + unique”, “smallest first”, “ascending order”

### ✅ Use

**TreeSet**

### 📌 Example

Store unique sorted numbers

### 💻 Code

```java
TreeSet<Integer> ts = new TreeSet<>();
ts.add(30);
ts.add(10);
ts.add(20);

System.out.println(ts);
```

### 🖨️ Output

```
[10, 20, 30]
```

### 🧠 Why it works

* TreeSet uses **Red-Black Tree**
* Automatically sorted

👉 **TRICK**: “sorted + no duplicates” = `TreeSet`

---

## 5️⃣ “just smaller”, “just greater”, “range queries”

### ✅ Use

**NavigableSet (TreeSet)**

### 📌 Example

Find just smaller element

### 💻 Code

```java
TreeSet<Integer> ts = new TreeSet<>(Arrays.asList(10,20,30));

System.out.println(ts.lower(20));
```

### 🖨️ Output

```
10
```

### 🧠 Why it works

* NavigableSet supports navigation (`lower`, `higher`)

👉 **TRICK**: boundaries / ranges = `TreeSet`

---

## 6️⃣ “ordered list”, “index-based”, “can repeat”

### ✅ Use

**ArrayList**

### 📌 Example

Store marks

### 💻 Code

```java
ArrayList<Integer> list = new ArrayList<>();
list.add(10);
list.add(20);
list.add(10);

System.out.println(list);
```

### 🖨️ Output

```
[10, 20, 10]
```

### 🧠 Why it works

* Order preserved
* Duplicates allowed
* Fast access by index

---

## 7️⃣ “frequent insert/delete in middle”

### ✅ Use

**LinkedList**

### 📌 Example

Insert at beginning

### 💻 Code

```java
LinkedList<Integer> list = new LinkedList<>();
list.add(10);
list.addFirst(5);

System.out.println(list);
```

### 🖨️ Output

```
[5, 10]
```

### 🧠 Why it works

* Doubly linked list
* No shifting like ArrayList

---

## 8️⃣ “undo”, “reverse”, “last in first out”

### ✅ Use

**Deque (ArrayDeque)**
*(NOT Stack in real code)*

### 📌 Example

Undo operations

### 💻 Code

```java
Deque<Integer> stack = new ArrayDeque<>();
stack.push(10);
stack.push(20);

System.out.println(stack.pop());
```

### 🖨️ Output

```
20
```

### 🧠 Why it works

* Deque supports stack operations
* Faster than legacy Stack

👉 **TRICK**: Stack word → actually use `Deque`

---

## 9️⃣ “first come first serve”, “queue”, “line”

### ✅ Use

**Queue (ArrayDeque / LinkedList)**

### 📌 Example

Customer queue

### 💻 Code

```java
Queue<Integer> q = new ArrayDeque<>();
q.offer(1);
q.offer(2);

System.out.println(q.poll());
```

### 🖨️ Output

```
1
```

### 🧠 Why it works

* FIFO behavior

---

## 🔟 “highest priority”, “smallest / largest first”, “top K”

### ✅ Use

**PriorityQueue**

### 📌 Example

Find smallest element first

### 💻 Code

```java
PriorityQueue<Integer> pq = new PriorityQueue<>();
pq.add(30);
pq.add(10);
pq.add(20);

System.out.println(pq.poll());
```

### 🖨️ Output

```
10
```

### 🧠 Why it works

* Min-heap by default

👉 **TRICK**: “top K”, “max/min” = `PriorityQueue`

---

## 1️⃣1️⃣ “sliding window”, “max in window”, “two ends”

### ✅ Use

**Deque (ArrayDeque)**

### 📌 Example

Add/remove from both ends

### 💻 Code

```java
Deque<Integer> dq = new ArrayDeque<>();
dq.addFirst(10);
dq.addLast(20);

System.out.println(dq);
```

### 🖨️ Output

```
[10, 20]
```

### 🧠 Why it works

* O(1) insertion/removal at both ends

---

## 1️⃣2️⃣ “key → value”, “mapping”, “dictionary”

### ✅ Use

**HashMap**

### 📌 Example

Roll number → name

### 💻 Code

```java
HashMap<Integer, String> map = new HashMap<>();
map.put(2, "B");
map.put(1, "A");

System.out.println(map);
```

### 🖨️ Output

```
{1=A, 2=B}
```

*(order may vary)*

### 🧠 Why it works

* Direct key-based lookup

---

## 1️⃣3️⃣ “sorted keys”, “range on keys”

### ✅ Use

**TreeMap**

### 💻 Code

```java
TreeMap<Integer,String> map = new TreeMap<>();
map.put(3,"C");
map.put(1,"A");

System.out.println(map);
```

### 🖨️ Output

```
{1=A, 3=C}
```

### 🧠 Why it works

* TreeMap keeps keys sorted

---

# 🧠 FINAL MASTER TRICK (EXAM GOLD)

```
frequency → HashMap
exist / seen → HashSet
remove duplicates → Set
sorted unique → TreeSet
range / just smaller → NavigableSet
ordered list → ArrayList
insert/delete heavy → LinkedList
undo / LIFO → Deque
FIFO → Queue
top / max / min → PriorityQueue
window → Deque
key-value → HashMap
sorted keys → TreeMap
```

---

## 🎯 HOW TO USE THIS IN EXAMS / INTERVIEWS

1. Read problem
2. Circle keywords
3. Match one row
4. Pick collection
5. Code confidently
