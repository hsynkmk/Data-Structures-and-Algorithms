# Module 05 — Searching

> Finding an element fast. The jump from O(n) to O(log n) is one of the great ideas in CS.

The headline act is **binary search** — and especially "binary search on the answer," a
pattern that solves problems that don't look like searching at all.

## Contents

| # | Algorithm | Time | Requires sorted? | Notes |
|---|-----------|------|------------------|-------|
| 01 | [Linear Search](01.Linear-Search.md) | O(n) | No | The baseline |
| 02 | [Binary Search](02.Binary-Search.md) | O(log n) | Yes | Halves the range each step (+ search-on-answer) |
| 03 | [Jump Search](03.Jump-Search.md) | O(√n) | Yes | Block jumps + linear scan |
| 04 | [Exponential Search](04.Exponential-Search.md) | O(log n) | Yes | Great for unbounded/infinite ranges |
| 05 | [Ternary Search](05.Ternary-Search.md) | O(log n) | Yes (or unimodal) | Splits in 3; also finds peaks of unimodal functions |

## After this module you can

- Implement binary search **without off-by-one bugs** (the hard part).
- Recognize when a problem is secretly "find the smallest X that works" → binary search the answer.
- Choose between binary/jump/exponential based on the data's shape.

> Prerequisite: an understanding of [Big-O](../00-Foundations/02.Big-O-and-Complexity.md) and
> why a [sorted](../04-Sorting/README.md) input enables O(log n).

---
◀ Prev: [04 — Sorting](../04-Sorting/README.md) · ▲ [Course home](../README.md) · ▶ Next: [06 — Algorithm Paradigms](../06-Algorithm-Paradigms/README.md)
