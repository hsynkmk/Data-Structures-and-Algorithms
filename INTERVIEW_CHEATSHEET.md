# 🚀 DSA Interview Cheat Sheet

**Read this the morning of the interview.** Every concept compressed to one line. If a row feels
rusty, jump to the full lesson:

[Foundations](00-Foundations/README.md) · [Linear](01-Linear-Structures/README.md) ·
[Trees & Heaps](02-Trees-and-Heaps/README.md) · [Graphs](03-Graphs/README.md) ·
[Sorting](04-Sorting/README.md) · [Searching](05-Searching/README.md) ·
[Paradigms](06-Algorithm-Paradigms/README.md) · [Strings](07-String-Algorithms/README.md) ·
[Patterns](08-Interview-and-Patterns/01.Problem-Solving-Patterns.md)

---

## 1. Big O — recognize at sight

| Pattern | Complexity |
|---------|-----------|
| Single loop over n | O(n) |
| Nested loops over n | O(n²) |
| Halving loop (`i /= 2`) | O(log n) |
| Recursion: 1 call, halves input | O(log n) |
| Recursion: 2 calls, n-1 input | O(2ⁿ) |
| Recursion: 2 calls, halved input + linear merge | O(n log n) |
| Permutations / brute-force TSP | O(n!) |

**Drop:** constants (`O(2n) → O(n)`) and non-dominant terms (`O(n² + n) → O(n²)`).

---

## 2. Data Structures — pick the right tool

| Need | Use |
|------|-----|
| Index access, fixed/known size | **Array** |
| Frequent insert/delete at ends, unknown size | **List** / **Linked List** |
| LIFO (parsing, backtracking, function calls) | **Stack** |
| FIFO (BFS, scheduling, buffering) | **Queue** |
| O(1) lookup by key | **Hash Table** (`Dictionary<K,V>`) |
| O(1) membership test, no duplicates | **Hash Set** (`HashSet<T>`) |
| Sorted, range queries, in-order traversal | **BST / SortedDictionary** |
| Get min/max in O(1), insert/remove in O(log n) | **Heap / Priority Queue** |
| Prefix matches, autocomplete | **Trie** |
| Relationships, networks | **Graph** |

### Operation complexity quick lookup
```
              Access  Search  Insert  Delete
Array         O(1)    O(n)    O(n)    O(n)
LinkedList    O(n)    O(n)    O(1)*   O(1)*    *at known node
Stack/Queue   O(n)    O(n)    O(1)    O(1)
HashTable     —       O(1)    O(1)    O(1)     (avg; worst O(n))
BST balanced  O(log)  O(log)  O(log)  O(log)
BST skewed    O(n)    O(n)    O(n)    O(n)
Heap          O(1)†   O(n)    O(log)  O(log)   †top only
Trie          —       O(L)    O(L)    O(L)     L = key length
```

---

## 3. Sorting — when to pick which

| Algorithm | Time | Space | Stable | Use it when |
|-----------|------|-------|--------|-------------|
| Insertion | O(n²) | O(1) | ✅ | n is small (<50) or nearly sorted |
| Merge | O(n log n) | O(n) | ✅ | Need stable sort, or external sort (huge files) |
| Quick | O(n log n) avg, O(n²) worst | O(log n) | ❌ | General-purpose, fastest in practice |
| Heap | O(n log n) | O(1) | ❌ | Need O(n log n) **worst-case** with O(1) memory |
| Counting | O(n + k) | O(k) | ✅ | Small integer range (k = range size) |
| Bucket | O(n + k) avg | O(n) | ✅ | Uniformly distributed inputs |

**Default real-world sort:** introsort (Quick + Heap fallback) — what `Array.Sort` uses in .NET.

---

## 4. Searching — pick by data shape

| Data | Use | Time |
|------|-----|------|
| Unsorted | Linear search | O(n) |
| Sorted (random access) | **Binary search** | O(log n) |
| Sorted, unbounded/infinite | Exponential search | O(log n) |
| Sorted, backward access expensive | Jump search | O(√n) |
| Hash key lookup | Hash table | O(1) avg |

---

## 5. Recursion / Trees — the patterns that show up

### Tree Traversals (memorize)
```csharp
// Preorder:  Root → Left → Right
// Inorder:   Left → Root → Right   (gives sorted output for BST!)
// Postorder: Left → Right → Root
// Level-order (BFS): use a queue

void Inorder(Node n) {
    if (n == null) return;
    Inorder(n.Left);
    Visit(n);
    Inorder(n.Right);
}

void LevelOrder(Node root) {
    var q = new Queue<Node>();
    q.Enqueue(root);
    while (q.Count > 0) {
        var n = q.Dequeue();
        Visit(n);
        if (n.Left  != null) q.Enqueue(n.Left);
        if (n.Right != null) q.Enqueue(n.Right);
    }
}
```

### BST property
For every node: `left.Value < node.Value < right.Value`. **Inorder traversal yields sorted output** — common interview trick.

---

## 6. Graphs — BFS vs DFS

| | BFS | DFS |
|---|-----|-----|
| Data structure | **Queue** | **Stack** (or recursion) |
| Finds | **Shortest path** in unweighted graphs | Any path; cycle detection; topo sort |
| Memory | O(width) | O(depth) |
| Use for | Shortest hops, level-order | Connectivity, ordering, backtracking |

```csharp
// BFS skeleton
void BFS(int start) {
    var visited = new HashSet<int> { start };
    var q = new Queue<int>(); q.Enqueue(start);
    while (q.Count > 0) {
        int v = q.Dequeue();
        foreach (int u in adj[v])
            if (visited.Add(u)) q.Enqueue(u);
    }
}

// DFS recursive
void DFS(int v, HashSet<int> visited) {
    if (!visited.Add(v)) return;
    foreach (int u in adj[v]) DFS(u, visited);
}
```

**Key graph algorithms (recognize the problem):**
- Shortest path, weighted non-negative → **Dijkstra** (heap-based)
- Shortest path, negative weights allowed → **Bellman-Ford**
- All-pairs shortest path → **Floyd-Warshall**
- Minimum spanning tree → **Kruskal** (Union-Find) or **Prim**
- Topological sort → DFS with finish order, or Kahn's BFS

---

## 7. Top Problem-Solving Patterns

| Pattern | When you see it | Example problems |
|---------|----------------|------------------|
| **Two pointers** | Sorted array, pair/triplet sum | Two Sum II, 3Sum, Container With Most Water |
| **Sliding window** | Subarray/substring with constraint | Longest Substring Without Repeating, Min Window |
| **Hash map for counting** | Frequencies, anagrams | Group Anagrams, Top K Frequent |
| **Hash map for "seen before"** | Two Sum, cycle detection | Two Sum, LRU |
| **Binary search on answer** | "Min/max value such that f(x) is feasible" | Capacity to Ship Packages, Koko Eating Bananas |
| **Stack** | Matching, "next greater element", parsing | Valid Parens, Daily Temperatures |
| **Monotonic stack/queue** | Next greater/smaller, sliding window max | Largest Rectangle in Histogram |
| **Heap / Top-K** | "K largest/smallest/most-frequent" | Kth Largest, Merge K Sorted Lists |
| **BFS** | Shortest path in unweighted graph/grid | Word Ladder, Rotting Oranges |
| **DFS / backtracking** | Generate all combinations | Permutations, Subsets, N-Queens |
| **DP** | "Count ways" / "min cost" / overlapping subproblems | Climb Stairs, Coin Change, LIS |
| **Union-Find** | Connectivity, grouping | Number of Islands II, Accounts Merge |

---

## 8. Recursion / DP — the framework

1. **Define the state** (what arguments uniquely determine a subproblem?)
2. **Write the recurrence** (how does the problem reduce to smaller versions of itself?)
3. **Base cases**
4. **Memoize** (top-down) or **tabulate** (bottom-up)
5. **Optimize space** if rows depend only on previous one or two

Classic DP recurrences:
- **Fib / Climb Stairs**: `f(n) = f(n-1) + f(n-2)`
- **Coin Change**: `dp[amt] = 1 + min(dp[amt - c]) for c in coins`
- **LIS** (longest increasing subseq): `dp[i] = 1 + max(dp[j]) for j < i, arr[j] < arr[i]` — O(n²); patience sort gives O(n log n)
- **Knapsack 0/1**: `dp[i][w] = max(dp[i-1][w], dp[i-1][w - wt[i]] + val[i])`
- **Edit Distance**: insert/delete/replace branching

---

## 9. C# things that trip people up

```csharp
// ✅ Use SortedDictionary / SortedSet for ordered traversal
var sd = new SortedDictionary<int, string>();

// ✅ PriorityQueue<TElement, TPriority> (.NET 6+) — min-heap by default
var pq = new PriorityQueue<int, int>();
pq.Enqueue(value: 42, priority: 5);

// ✅ Tuples for multi-return
(int min, int max) GetBounds(int[] arr) => (arr.Min(), arr.Max());

// ✅ Swap without temp
(a, b) = (b, a);

// ⚠️ Reference vs value: int[] copy = original  →  same reference!
//    Use Array.Copy or arr.ToArray() for a real copy.

// ⚠️ Dictionary access with [] throws on missing key
//    Use TryGetValue or ContainsKey for safe lookup.
```

---

## 10. 60-Second Interview Sanity Checklist

Before you start coding:
- [ ] Restated the problem in your own words
- [ ] Asked about input bounds, edge cases (empty? negatives? duplicates?)
- [ ] Stated the brute-force first, then proposed an optimization
- [ ] Discussed time + space complexity **before** writing code

While coding:
- [ ] Named variables clearly (`left/right`, not `l/r`)
- [ ] Walked through one example at the whiteboard
- [ ] Mentioned trade-offs out loud — interviewers grade your **thinking**, not just your code

After coding:
- [ ] Trace through a non-trivial example
- [ ] Mention edge cases (empty, single element, all duplicates, max input)
- [ ] State final time + space complexity

---

> "Algorithms are not memorized. They are recognized."  
> Pick the **pattern**, not the solution.
