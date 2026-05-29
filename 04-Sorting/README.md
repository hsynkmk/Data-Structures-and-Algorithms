# Module 04 — Sorting

> Sorting is the classic playground for understanding algorithmic trade-offs.

You'll rarely write a sort in production (the standard library has you covered), but
*understanding* them teaches divide-and-conquer, stability, in-place vs extra memory, and
why "O(n log n)" is a wall for comparison sorts.

## Contents (simple → advanced)

| # | Algorithm | Best | Avg | Worst | Space | Stable | Notes |
|---|-----------|------|-----|-------|-------|--------|-------|
| 01 | [Bubble Sort](01.Bubble-Sort.md) | O(n) | O(n²) | O(n²) | O(1) | ✅ | Teaching only |
| 02 | [Selection Sort](02.Selection-Sort.md) | O(n²) | O(n²) | O(n²) | O(1) | ❌ | Fewest swaps |
| 03 | [Insertion Sort](03.Insertion-Sort.md) | O(n) | O(n²) | O(n²) | O(1) | ✅ | Great for small/nearly-sorted |
| 04 | [Merge Sort](04.Merge-Sort.md) | O(n log n) | O(n log n) | O(n log n) | O(n) | ✅ | Predictable, external sort |
| 05 | [Quick Sort](05.Quick-Sort.md) | O(n log n) | O(n log n) | O(n²) | O(log n) | ❌ | Fastest in practice |
| 06 | [Heap Sort](06.Heap-Sort.md) | O(n log n) | O(n log n) | O(n log n) | O(1) | ❌ | In-place, no bad case |
| 07 | [Counting Sort](07.Counting-Sort.md) | O(n+k) | O(n+k) | O(n+k) | O(k) | ✅ | Integers in known range |
| 08 | [Radix Sort](08.Radix-Sort.md) | O(d·(n+k)) | O(d·(n+k)) | O(d·(n+k)) | O(n+k) | ✅ | Beats O(n log n) for fixed-width keys |
| 09 | [Bucket Sort](09.Bucket-Sort.md) | O(n+k) | O(n+k) | O(n²) | O(n) | ✅ | Uniformly distributed data |

## Which sort when?

- **Tiny or nearly-sorted array** → Insertion Sort.
- **Need guaranteed O(n log n) & stability** → Merge Sort.
- **General-purpose, fastest average** → Quick Sort (what most libraries use, hybridized).
- **Guaranteed O(n log n), O(1) space** → Heap Sort.
- **Integers / keys in a small known range** → Counting or Radix Sort (beat the comparison wall).

> The O(n log n) lower bound applies to **comparison** sorts. Counting/Radix/Bucket sidestep it
> by *not comparing* elements — see [Big-O](../00-Foundations/02.Big-O-and-Complexity.md).

---
◀ Prev: [03 — Graphs](../03-Graphs/README.md) · ▲ [Course home](../README.md) · ▶ Next: [05 — Searching](../05-Searching/README.md)
