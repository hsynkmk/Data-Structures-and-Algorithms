# Module 07 — String Algorithms

> Searching text fast. Naive substring search is O(n·m) — these algorithms make it O(n+m).

Strings are everywhere (search engines, DNA, log parsing). The pattern-matching algorithms
here are also beautiful examples of *precomputation* — doing clever work up front to avoid
repeated work later.

## Contents

| # | Topic | One-liner |
|---|-------|-----------|
| 01 | [Pattern Matching](01.Pattern-Matching.md) | KMP, Rabin-Karp, and the Z-algorithm |

## After this module you can

- Explain why naive search is slow and how KMP's failure function avoids re-scanning.
- Use rolling hashes (Rabin-Karp) for fast average-case and multi-pattern search.
- Apply the Z-algorithm for prefix-matching problems.

> Prerequisite: [Strings](../01-Linear-Structures/02.Strings.md) and [Hash Tables](../01-Linear-Structures/06.Hash-Tables.md).

---
◀ Prev: [06 — Algorithm Paradigms](../06-Algorithm-Paradigms/README.md) · ▲ [Course home](../README.md) · ▶ Next: [08 — Interview & Patterns](../08-Interview-and-Patterns/README.md)
