# Binary Number Triangle Pattern

## Problem Statement

Create a triangle pattern using **alternating 0s and 1s** for n rows.  
Each row should start with:
- 1 if the row number is **odd**
- 0 if the row number is **even**

Subsequent values in the row **alternate** between 1 and 0.

---

## Approach

We use nested loops:
- Outer loop runs from 1 to n to control the number of rows.
- Inner loop runs from 1 to i to print each element in the row.

Use a variable start to determine the starting digit:
- If the row number i is odd → start with 1
- If even → start with 0

#### Python Code:
```python
def nStarDiamond(n: int) -> None:
    # Upper half of the diamond
    for i in range(1, n + 1):
        print(" " * (n - i) + "*" * (2 * i - 1))
    
    # Lower half of the diamond
    for i in range(n - 1, 0, -1):
        print(" " * (n - i) + "*" * (2 * i - 1))

```
---

### Sample Input:
n = 5

### sample Output:
```
1
0 1
1 0 1
0 1 0 1
1 0 1 0 1

```

---

### Complexity Analysis:
**Time Complexity:** O(n²)
Outer loop runs n times.

Inner loop runs up to n times per row.

Total prints ≈ n(n + 1)/2

**Space Complexity:** O(1)

---

### Learning Outcomes:
How to toggle between binary digits using 1 - start.

Nested loop practice with conditional logic.

Understanding of how row number influences pattern rules.
