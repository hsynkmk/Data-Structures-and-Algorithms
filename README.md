# Data Structures & Algorithms (C#)

A focused reference of data structures, sorting & searching algorithms — implemented in C#, with complexity analysis, common pitfalls, and interview-style notes.

> 🎯 **Crunched for time before an interview?** Start with the [Interview Cheat Sheet](INTERVIEW_CHEATSHEET.md) — every structure and algorithm boiled down to one row.

---

## ⚡ Big O at a Glance

| Notation | Name | Example |
|----------|------|---------|
| O(1) | Constant | Array access, hash lookup |
| O(log n) | Logarithmic | Binary search, balanced BST ops |
| O(n) | Linear | Single loop, linear search |
| O(n log n) | Linearithmic | Merge sort, heap sort, quick sort (avg) |
| O(n²) | Quadratic | Bubble sort, selection sort, nested loops |
| O(2ⁿ) | Exponential | Naive recursive Fibonacci, brute-force subsets |
| O(n!) | Factorial | Permutations, brute-force TSP |

Read more → [01.BigONotation.md](DataStructures/01.BigONotation.md)

---

## 📚 Data Structures

### Linear
| Structure | Access | Search | Insert | Delete | Notes |
|-----------|--------|--------|--------|--------|-------|
| [Array](DataStructures/02.Arrays.md) | O(1) | O(n) | O(n) | O(n) | Fixed size, cache-friendly |
| [Linked List](DataStructures/03.LinkedLists.md) | O(n) | O(n) | O(1)* | O(1)* | *at known node |
| [Stack](DataStructures/04.Stacks.md) | O(n) | O(n) | O(1) | O(1) | LIFO |
| [Queue](DataStructures/05.Queues.md) | O(n) | O(n) | O(1) | O(1) | FIFO |
| [Hash Table](DataStructures/06.HashTables.md) | — | O(1) avg | O(1) avg | O(1) avg | Worst O(n) on bad hash |

### Tree-Based
| Structure | Search | Insert | Delete | Notes |
|-----------|--------|--------|--------|-------|
| [Binary Tree / BST](DataStructures/07.BinaryTrees.md) | O(log n) avg, O(n) worst | same | same | Skewed tree → O(n) |
| [AVL Tree](DataStructures/08.AVL_Trees.md) | O(log n) | O(log n) | O(log n) | Self-balancing BST |
| [Heap](DataStructures/09.Heap.md) | O(n) | O(log n) | O(log n) | Min/Max access O(1) |
| [Trie](DataStructures/10.Trias.md) | O(L) | O(L) | O(L) | L = key length, prefix search |

### Graph
- [Graphs (directed)](DataStructures/11.Graphs.md)
- [Undirected Graphs](DataStructures/12.UndirectedGraphs.md)

---

## 🔄 Sorting Algorithms

| Algorithm | Best | Avg | Worst | Space | Stable | Notes |
|-----------|------|-----|-------|-------|--------|-------|
| [Bubble Sort](SortingAlgorithms/BubbleSort.md) | O(n) | O(n²) | O(n²) | O(1) | ✅ | Teaching only |
| [Selection Sort](SortingAlgorithms/SelectionSort.md) | O(n²) | O(n²) | O(n²) | O(1) | ❌ | Min swaps |
| [Insertion Sort](SortingAlgorithms/InsertionSort.md) | O(n) | O(n²) | O(n²) | O(1) | ✅ | Great for small/nearly-sorted |
| [Merge Sort](SortingAlgorithms/MergeSort.md) | O(n log n) | O(n log n) | O(n log n) | O(n) | ✅ | Predictable, external sort |
| [Quick Sort](SortingAlgorithms/QuickSort.md) | O(n log n) | O(n log n) | O(n²) | O(log n) | ❌ | Fastest in practice |
| [Heap Sort](SortingAlgorithms/HeapSort.md) | O(n log n) | O(n log n) | O(n log n) | O(1) | ❌ | In-place, no worst case |
| [Counting Sort](SortingAlgorithms/CountingSort.md) | O(n+k) | O(n+k) | O(n+k) | O(k) | ✅ | Integers in known range |
| [Bucket Sort](SortingAlgorithms/BucketSort.md) | O(n+k) | O(n+k) | O(n²) | O(n) | ✅ | Uniform distribution |

---

## 🔍 Searching Algorithms

| Algorithm | Time | Requires Sorted? | Notes |
|-----------|------|------------------|-------|
| [Linear Search](SearchingAlgorithms/LinearSearch.md) | O(n) | No | Simplest |
| [Binary Search](SearchingAlgorithms/BinarySearch.md) | O(log n) | Yes | Halves range |
| [Ternary Search](SearchingAlgorithms/TernarySearch.md) | O(log₃ n) | Yes | Splits in 3, more comparisons |
| [Jump Search](SearchingAlgorithms/JumpSearch.md) | O(√n) | Yes | Block + linear |
| [Exponential Search](SearchingAlgorithms/ExponentialSearch.md) | O(log n) | Yes | Good for unbounded/infinite arrays |

---

## 🗺️ Recommended Study Order (interview prep)

1. **Big O Notation** — frame everything else
2. **Arrays + Linked Lists** — building blocks
3. **Stacks + Queues** — used everywhere (BFS, DFS, expressions)
4. **Hash Tables** — the secret weapon for O(1) lookups
5. **Trees + BST + Heaps** — recursion, traversals, priority queues
6. **Sorting (Merge / Quick / Heap)** — and *why* they differ
7. **Binary Search** — including its less-obvious applications
8. **Graphs (BFS / DFS)** — wide variety of problems

---

## 🤝 Contributing

PRs welcome — open an issue or fork & submit.
