# Ternary Search

## 🧠 What It Is
Like binary search, but split the range into **three** parts using two midpoints `m1` and `m2`:

```
[low ........ m1 ........ m2 ........ high]
        \           |            /
       left      middle       right
```

- If `target == arr[m1]` or `arr[m2]` → found
- If `target < arr[m1]`        → search `low..m1-1`
- If `target > arr[m2]`        → search `m2+1..high`
- Otherwise                    → search `m1+1..m2-1`

## 📊 Complexity
| Case | Time | Space |
|------|------|-------|
| Best | O(1) | O(1) |
| Average / Worst | O(log₃ n) | O(1) |

`log₃ n` is asymptotically the same class as `log₂ n` — but ternary search does **more comparisons per step** (up to 4) vs binary search's 2, so **binary search wins in practice** for sorted-array lookup.

## 🚀 C# Implementation
```csharp
public static int TernarySearch(int[] arr, int target)
{
    int low = 0, high = arr.Length - 1;
    while (low <= high)
    {
        int third = (high - low) / 3;
        int m1 = low + third;
        int m2 = high - third;

        if (arr[m1] == target) return m1;
        if (arr[m2] == target) return m2;

        if (target < arr[m1])      high = m1 - 1;
        else if (target > arr[m2]) low  = m2 + 1;
        else { low = m1 + 1; high = m2 - 1; }
    }
    return -1;
}
```

## 🌟 Where It Shines: Unimodal Functions
Ternary search **really** earns its keep finding the **maximum (or minimum) of a unimodal function** — a function that strictly increases then strictly decreases (or vice versa). Binary search can't do that.

```csharp
// Find x in [lo, hi] that maximizes f(x), assuming f is unimodal
public static double TernarySearchMax(Func<double, double> f, double lo, double hi)
{
    for (int i = 0; i < 200; i++) // ~200 iters → ~1e-30 precision
    {
        double m1 = lo + (hi - lo) / 3;
        double m2 = hi - (hi - lo) / 3;
        if (f(m1) < f(m2)) lo = m1;
        else               hi = m2;
    }
    return (lo + hi) / 2;
}
```

## 🚫 Common Mistakes
- Using it as a drop-in replacement for binary search expecting it to be *faster*. It isn't.
- Applying it to non-unimodal functions (gives wrong answers silently).

## 📚 Key Takeaways
1. Same big-O class as binary search but **slower in practice** for array lookup
2. **Real use case**: optimizing **unimodal** continuous functions
3. Common in competitive programming, less so in day-to-day code
