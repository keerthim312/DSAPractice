# Star Triangle Diamond Pattern

## Problem Statement

Create a star (`*`) pattern that forms a **vertical diamond**, using nested loops. The pattern consists of:

- An **upper triangle** with increasing stars
- A **lower triangle** (mirrored) with decreasing stars

The output is **left-aligned** (not centered).

---

## Approach

This pattern is built using **two parts**:

1. **Upper half** of the diamond:  
   Print increasing number of stars from 1 to n.

2. **Lower half** of the diamond:  
   Print decreasing number of stars from n-1 down to 1.

Each line consists of only stars (`*`) with no leading spaces, making it left-aligned.

---

## Python Code

```python
def nStarTriangle(n: int) -> None:
    # Upper half of the diamond
    for i in range(1, n + 1):
        for j in range(1, i + 1):
            print("*", end = "")
        print()

    # Lower half of the diamond
    for i in range(n - 1, 0, -1):
        for j in range(1, i + 1):
            print("*", end = "")
        print()

```
---

### Sample Input:
n = 3

### sample Output:
```
*
**
***
**
*

```

---

### Complexity Analysis:
**Time Complexity:** O(n²)
The outer loop runs 2n - 1 times (for upper and lower parts).

The inner loop can run up to n times per row.

Total star prints ≈ n² operations.

**Space Complexity:** O(1)
Only loop counters and n are used

---
This diamond pattern is a classic example for:

Learning how to adjust spaces dynamically.
