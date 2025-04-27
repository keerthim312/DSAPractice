# Symmetry Pattern

## Problem Statement

Generate a symmetric pattern using `*` and spaces for a given integer `n`. The final pattern is a square of size `2n x 2n`, where the symmetry appears both vertically and horizontally.

The pattern consists of:
- An upper half and a lower half.
- Each half mirrors the other.
- The stars create a symmetric "X"-like design with spaces between.

---

## Approach

1. Multiply `n` by 2 to get the full pattern size.
2. Loop over each row from `0` to `2n - 1`.
3. For each row:
   - Loop over each column from `0` to `2n - 1`.
   - Use conditional checks to print `*` or space (`" "`), based on whether the column is in the outer region or inner region of that row.

---

## Python Code

```python
def symmetry(n: int): 
    # Update n to represent the full size of the square
    n = 2 * n

    # Loop through each row
    for row in range(n):
        # Loop through each column
        for col in range(n):
            # Upper half condition
            if row < n // 2 and (col < (n // 2 - row) or col >= (n // 2 + row)):
                print('*', end=" ")
            # Lower half condition
            elif row >= n // 2 and (col <= (row - n // 2) or col >= (n - row + n // 2 - 1)):
                print('*', end=" ")
            # Inner region (spaces)
            else:
                print(" ", end=" ")
        print()

```
---

### Sample Input:
n = 3

### sample Output:
```
* * * * * * 
* *     * * 
*         * 
*         * 
* *     * * 
* * * * * * 


```

---

### Complexity Analysis:
**Time Complexity:** O(n²)
Every cell in a 2n x 2n grid is checked and printed
**Space Complexity:** O(1)
Only loop counters and constants are used. No extra space.

---
### Learning Outcomes:
Practice with complex nested loop conditions.

Learn symmetry and pattern construction.

Use conditional logic for visual pattern design.

Improve understanding of 2D grid-based pattern logic.

---

