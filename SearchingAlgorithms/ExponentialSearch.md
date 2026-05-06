# Exponential Search

## 🧠 What It Is
For **sorted** arrays — especially **unbounded / infinite** ones (where you don't know the size up front):

1. **Find a range** containing the target by doubling the index: `1, 2, 4, 8, 16, ...` until `arr[i] >= target` (or end).
2. **Binary search** within that range.

```
range expansion:  1 → 2 → 4 → 8 → 16  (target falls between 8 and 16)
binary search:    [8 .. 15]
```

## 📊 Complexity
| Step | Cost |
|------|------|
| Range finding | O(log i) — i = position of target |
| Binary search in range | O(log i) |
| **Total** | **O(log n)** |

| Case | Time | Space |
|------|------|-------|
| Best | O(1) | O(1) |
| Average / Worst | O(log n) | O(1) |

Same asymptotic class as binary search, but **better when the target is near the start** of a very large (or unbounded) array.

## 🚀 C# Implementation
```csharp
public static int ExponentialSearch(int[] arr, int target)
{
    int n = arr.Length;
    if (n == 0) return -1;
    if (arr[0] == target) return 0;

    // Phase 1: find range by doubling
    int i = 1;
    while (i < n && arr[i] <= target) i *= 2;

    // Phase 2: binary search in [i/2 .. min(i, n-1)]
    return BinarySearch(arr, target, i / 2, Math.Min(i, n - 1));
}

private static int BinarySearch(int[] arr, int target, int low, int high)
{
    while (low <= high)
    {
        int mid = low + (high - low) / 2;
        if (arr[mid] == target) return mid;
        if (arr[mid] < target) low = mid + 1;
        else                   high = mid - 1;
    }
    return -1;
}
```

## ✅ When to Use
- **Unbounded arrays / streams** (e.g., a sorted stream where the length isn't known)
- Sorted arrays where the target is likely **near the beginning**
- LeetCode-style: "Search in a sorted infinite array"

## 🚫 Common Mistakes
- Forgetting the `i < n` guard during doubling → IndexOutOfRange
- Setting the binary search lower bound to `0` instead of `i / 2` (correct but wasteful)

## 🏋️ Practice
- "Search in a Sorted Array of Unknown Size" — premium LeetCode 702

## 📚 Key Takeaways
1. **O(log n)** — same class as binary search
2. Wins when **size is unknown** (infinite/unbounded arrays)
3. Wins when target is **near the start**
4. Two phases: double until overshoot, then binary search
