# Hollow Square Star Pattern

## Problem Statement

Write a function `getStarPattern(n)` that prints a **hollow square pattern** of size `n × n` using stars (`*`).

- Stars are printed on the **border** (first and last rows and columns).
- **Spaces** are printed inside (non-border positions).

---

## Approach

1. Loop through each row `i` from `0` to `n - 1`.
2. Inside each row, loop through each column `j` from `0` to `n - 1`.
3. Print `*` if:
   - `i == 0` (first row)
   - `j == 0` (first column)
   - `i == n - 1` (last row)
   - `j == n - 1` (last column)
4. Else, print `" "` (space).
5. Move to the next line after each row.

---

## Python Code

```python
def getStarPattern(n: int) -> None:
    for i in range(n):
        for j in range(n):
            if i == 0 or j == 0 or i == n - 1 or j == n - 1:
                print("*", end="")
            else:
                print(" ", end="")
        print()

```
---

### Sample Input:
n = 5

### sample Output:
```

*****
*   *
*   *
*   *
*****

```

---

### Complexity Analysis:
**Time Complexity:** O(n²)
Each of the n rows prints n characters.

**Space Complexity:** O(1)
No extra space used other than loop variables.

---
### Learning Outcomes:
Practice basic pattern generation.

Understand boundary conditions in nested loops.

Learn the use of logical OR conditions (or) to handle multiple cases.


---