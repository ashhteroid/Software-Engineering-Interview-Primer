# Dynamic Programming Intuition: Restating Problems & Reducing Dimensions

## 1. Original Problem
**Find the contiguous subarray with the maximum sum.**

This problem appears 2-dimensional because a subarray is defined by:
- a **start index**
- an **end index**

Total possible subarrays: **O(n²)**.

Dynamic programming reduces this to **O(n)** by fixing one dimension.

---

# 2. DP Subproblem Selection – The Key Insight

## Why fix the *end index*?
Contiguity flows **forward**:

```
If a subarray ends at index i,
its previous element must be index i–1.
```

So the recurrence depends locally on i−1.

Fixing the **start** does NOT work:
- the end could be anywhere in the future  
- too many possibilities  
- you would need to scan forward  

Fixing the **end** creates:
- a clean local recurrence
- a single optimal choice at each step  
- a 1D chain of subproblems

---

# 3. Example A — Maximum Subarray (Kadane's Algorithm)

## A. Restating the Problem Until DP Emerges

### Original
Find the maximum-sum contiguous subarray.

### Restatement 1
Consider all subarrays ending at any index.

### Restatement 2
For a specific index i, what is the best subarray ending *exactly* at i?

### Restatement 3
A subarray ending at i has only two possibilities:

1. It starts at i → arr[i]
2. It extends the best subarray ending at i−1 → arr[i] + dp[i-1]

Recurrence:

```
dp[i] = max(arr[i], arr[i] + dp[i-1])
```

Final answer:
```
max(dp[i])
```

---

# 4. Example B — Longest Increasing Subsequence (LIS)

## A. Restating LIS Step-by-Step

### Original
Find the longest strictly increasing subsequence.

### Restatement 1
Consider all increasing subsequences ending anywhere.

### Restatement 2
For a specific index i, define the longest increasing subsequence that *ends at i*.

### Restatement 3
To build an LIS ending at i, extend any earlier LIS ending at j if arr[j] < arr[i]:

```
dp[i] = 1 + max(dp[j]) for all j < i where arr[j] < arr[i]
```

If no such j exists:
```
dp[i] = 1
```

### Restatement 4
Global answer:
```
max(dp[i])
```

---

# 5. General DP Pattern Learned

- DP emerges naturally when you repeatedly restate the problem until you reach a formulation that:
  - fixes one dimension
  - has forced structure
  - has a local recurrence
  - reuses previous results

- Fixing a dimension collapses multi-dimensional reasoning.

- The “end index” is often the correct dimension to fix.

---

# 6. Final Summary

| Concept | Max Subarray | LIS |
|--------|--------------|-----|
| Original problem | Best contiguous subarray | Best increasing subsequence |
| Natural dimensions | (start, end) | (prev_index, current_index) |
| Dimension to fix | **end** | **end** |
| Subproblem | best sum ending at i | best LIS ending at i |
| Recurrence | extend or restart | extend any valid j < i |
| Complexity drop | O(n²) → O(n) | O(n²) → O(n²) or O(n log n) |
| Why starting index disappears | encoded in “restart or extend” | encoded in “choose j that leads to best result” |

The key mental model:

**DP is the art of reducing a multi-dimensional search space  
by fixing one dimension until the recurrence becomes local.**
