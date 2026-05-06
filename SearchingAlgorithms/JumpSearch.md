# Jump Search

## 🧠 What It Is
A compromise between linear and binary search on **sorted** arrays:

1. Jump ahead in fixed-size blocks of `√n` until you overshoot the target.
2. Linearly scan **backwards** within the last block.

```
arr: [1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 21, 23, 25] (n=13, step=√13≈4)
         jump → idx 0, 4, 8, 12  → first idx where arr[idx] > target
         then linear scan inside that block
```

## 📊 Complexity
| Step | Cost |
|------|------|
| Number of jumps | n / √n = √n |
| Linear scan inside block | √n |
| **Total** | **O(√n)** |

| Case | Time | Space |
|------|------|-------|
| Best | O(1) | O(1) |
| Average / Worst | O(√n) | O(1) |

- **Requires sorted input.**

## 🚀 C# Implementation
```csharp
public static int JumpSearch(int[] arr, int target)
{
    int n = arr.Length;
    int step = (int)Math.Floor(Math.Sqrt(n));
    int prev = 0;

    // Phase 1: jump
    while (arr[Math.Min(step, n) - 1] < target)
    {
        prev = step;
        step += (int)Math.Floor(Math.Sqrt(n));
        if (prev >= n) return -1;
    }

    // Phase 2: linear scan inside block
    while (arr[prev] < target)
    {
        prev++;
        if (prev == Math.Min(step, n)) return -1;
    }
    return arr[prev] == target ? prev : -1;
}
```

## ✅ Why It Exists
- **Binary search**: O(log n), but **jumps backwards** — bad for systems where backward access is expensive (tape drives, slow disk).
- **Linear search**: only forward, but O(n).
- **Jump search**: only forward jumps + small backward scan → O(√n).

In modern RAM-based systems, binary search almost always beats it.

## 🚫 Common Mistakes
- Using a step size that isn't `√n` (worse complexity)
- Forgetting to clamp `Math.Min(step, n)` → IndexOutOfRange

## 📚 Key Takeaways
1. **O(√n)** — between linear and binary
2. Useful when **backward access is costly**
3. Optimal block size is `√n`
4. Mostly historical / educational interest today
