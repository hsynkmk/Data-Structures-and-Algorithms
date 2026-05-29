# Linear Search

## 🧠 What It Is
Walk the array from start to end, comparing each element to the target. Return the first match (or -1).

## 📊 Complexity
| Case | Time | Space |
|------|------|-------|
| Best | O(1) | O(1) |
| Average | O(n) | O(1) |
| Worst | O(n) | O(1) |

- **Sorted input?** Not required.
- **Stable?** Not applicable (search, not sort).

## ✅ When to Use
- Small arrays (cache locality often beats `O(log n)` for n < ~50)
- Unsorted data
- Linked lists (no random access → can't binary search)
- One-shot search where sorting cost > linear scan cost

## 🚀 C# Implementation
```csharp
public static int LinearSearch<T>(T[] arr, T target)
{
    for (int i = 0; i < arr.Length; i++)
    {
        if (EqualityComparer<T>.Default.Equals(arr[i], target))
            return i;
    }
    return -1;
}
```

### Sentinel Variant (one comparison per iteration)
```csharp
public static int LinearSearchSentinel(int[] arr, int target)
{
    int last = arr[arr.Length - 1];
    arr[arr.Length - 1] = target;          // sentinel

    int i = 0;
    while (arr[i] != target) i++;

    arr[arr.Length - 1] = last;             // restore
    return (i < arr.Length - 1 || last == target) ? i : -1;
}
```

## 🚫 Common Mistakes
- Returning `0` instead of `-1` for "not found" (loses info — index 0 is valid)
- Using `==` on reference types where you wanted `.Equals`

## 🏋️ Practice
- [Find First and Last Position of Element in Sorted Array](https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/) (use binary, but compare!)
- [Two Sum](https://leetcode.com/problems/two-sum/) (linear + hash)

## 📚 Key Takeaways
1. Simplest possible search — always works
2. O(n) regardless of order
3. Beats binary search for **small** or **unsorted** data
4. The fallback when nothing else applies
