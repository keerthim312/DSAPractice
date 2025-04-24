# Number Crown Pattern

## Problem Statement

Generate a **number crown pattern** for a given integer n.  
Each row contains:
- Increasing numbers from 1 to i
- A set of spaces that decreases each row
- Decreasing numbers from i down to 1

This forms a **mirrored number pyramid** with a "crown" shape.

---

## Approach

To create the crown pattern:
1. Loop through each row i from 1 to n.
2. For each row:
   - Print numbers increasing from 1 to i.
   - Print spaces equal to 2 * (n - i) to separate the left and right side.
   - Print numbers decreasing from i to 1.

The pattern is symmetric around the central gap of spaces.

---

## Python Code

```python
def numberCrown(n: int) -> None:
    # Loop through each row
    for i in range(1, n + 1):
        # Left side numbers (increasing)
        for j in range(1, i + 1):
            print(j, end = " ")

        # Middle spaces
        spaces = 2 * (n - i)
        print(" " * spaces, end = "")

        # Right side numbers (decreasing)
        for j in range(i, 0, -1):
            print(j, end = " ")

        print()  # Move to next line

```
---

### Sample Input:
n = 3

### sample Output:
```
1         1 
1 2     2 1 
1 2 3 3 2 1 


```

---

### Complexity Analysis:
**Time Complexity:** O(n²)
Each row prints i numbers, some spaces, then i more numbers.

Total work is quadratic in terms of n.

**Space Complexity:** O(1)
Uses only loop variables and a constant amount of memory.

---
### Learning Outcomes:
Practice with nested loops for symmetric patterns.

Use of increasing/decreasing loops in the same row.

Learn how to align patterns using calculated spacing.

---

