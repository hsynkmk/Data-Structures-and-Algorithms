# Data Structures & Algorithms — A Complete Course (C#)

> **Read this repo top to bottom and you won't need another DSA resource.**
> Every topic starts with plain-English intuition, builds up to clean C# code, and ends with
> hand-picked problems **solved in full**. No prior DSA knowledge assumed.

This isn't a loose reference — it's an **ordered curriculum**. The folders are numbered
`00 → 08`. Read them in order and each topic only relies on things you've already learned.

🎯 **In a hurry before an interview?** Jump to the [Interview Cheat Sheet](INTERVIEW_CHEATSHEET.md).
🧭 **New here?** Start with [How to Use This Repo](00-Foundations/01.How-To-Use-This-Repo.md).

---

## 🗺️ The Curriculum

| # | Module | What you'll learn | Why it's here |
|---|--------|-------------------|---------------|
| **00** | [Foundations](00-Foundations/README.md) | Big-O, recursion, bit manipulation | The lens you'll view everything else through |
| **01** | [Linear Structures](01-Linear-Structures/README.md) | Arrays, strings, linked lists, stacks, queues, hash tables | The building blocks of every program |
| **02** | [Trees & Heaps](02-Trees-and-Heaps/README.md) | BST, traversals, AVL, heaps, tries, union-find, segment trees | Hierarchies, priorities, and fast range/set ops |
| **03** | [Graphs](03-Graphs/README.md) | Representations, BFS/DFS, topo sort, shortest paths, MST | Modeling relationships and networks |
| **04** | [Sorting](04-Sorting/README.md) | 9 sorting algorithms + when to use which | The classic lens on trade-offs |
| **05** | [Searching](05-Searching/README.md) | Linear, binary (+ on the answer), jump, exponential, ternary | Finding things fast |
| **06** | [Algorithm Paradigms](06-Algorithm-Paradigms/README.md) | Two pointers, sliding window, prefix sums, divide & conquer, backtracking, greedy, DP | **How to actually solve problems** |
| **07** | [String Algorithms](07-String-Algorithms/README.md) | KMP, Rabin-Karp, Z-algorithm | Pattern matching at scale |
| **08** | [Interview & Patterns](08-Interview-and-Patterns/README.md) | Pattern catalog, study plan, cheat sheet | Tying it all together |

---

## ⚡ Big-O at a Glance

| Notation | Name | Example |
|----------|------|---------|
| O(1) | Constant | Array access, hash lookup |
| O(log n) | Logarithmic | Binary search, balanced BST ops |
| O(n) | Linear | Single loop, linear search |
| O(n log n) | Linearithmic | Merge sort, heap sort, quick sort (avg) |
| O(n²) | Quadratic | Bubble sort, nested loops |
| O(2ⁿ) | Exponential | Naive recursive Fibonacci, brute-force subsets |
| O(n!) | Factorial | Permutations, brute-force TSP |

Full explanation → [Big-O and Complexity](00-Foundations/02.Big-O-and-Complexity.md)

---

## 🧭 How to Study This

1. **Don't skip Foundations.** Big-O and recursion are the vocabulary for everything after.
2. **Read actively.** When you hit the 🧾 Pseudocode, cover the C# and try to write it yourself.
3. **Do the 🎯 Practice.** Attempt each problem *before* reading the solution. The solution is
   right there when you get stuck — that's the point.
4. **Use the self-check questions** at the end of each file as your "am I ready to move on?" gate.
5. **Loop back via** [Module 08](08-Interview-and-Patterns/README.md) once you've covered the
   structures — it maps problem *signals* to the right technique.

A concrete week-by-week roadmap lives in the [Study Plan](08-Interview-and-Patterns/02.Study-Plan.md).

---

## 📐 How Each Topic Is Structured

Every file follows the same shape — intuition → how it works → pseudocode → C# → complexity →
trade-offs → mistakes → applications → **practice with full solutions** → takeaways. See
[TEMPLATE.md](TEMPLATE.md) for the full spec (and use it if you contribute).

---

## 🤝 Contributing

PRs welcome. New topics must follow [TEMPLATE.md](TEMPLATE.md) so the learning curve stays
consistent. Open an issue first for anything large.
