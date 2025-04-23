# Centered Star Triangle Pattern Problem

## Approach:
[Centered Pyramid Shape using Nested Loops]

---

### 1. Simple Nested Loop for Star Triangle

#### Intuition:
This pattern prints a **centered pyramid** of stars, where each row contains an **odd number of stars**, increasing as the row number increases.

- The outer loop runs from 1 to n, controlling the number of rows.
- Each row consists of:
  - **Spaces** on the left to center the stars: (n - i) spaces
  - **Stars** in the middle: 2*i - 1 stars
  - **Optional right spaces** for symmetry (can be skipped as not needed for visual alignment)

This pattern is often used in pyramid-like visual problems and helps reinforce loop nesting and condition-based character printing.

---

#### Python Code:
```python
def nStarTriangle(n: int) -> None:
    for i in range(1, n + 1):
        # Print left spaces
        for j in range(1, n + 1 - i):
            print(" ", end="")
        
        # Print stars
        for j in range(1, 2 * i):
            print("*", end="")
        
        # Optional: Print right spaces for symmetry
        for j in range(1, n + 1 - i):
            print(" ", end="")
        
        # Move to the next line
        print()
```
---

### Sample Input:
n = 3

### sample Output:
```
  *  
 *** 
*****

```

---

### Complexity Analysis:
**Time Complexity:** O(n²)
The outer loop runs n times.
Inner loops (spaces + stars) contribute to ≈ 2n operations per row in the worst case.
**Space Complexity:** O(1)
Constant space is used, not counting the output.

---

This triangle pattern is a classic pyramid used in interviews and competitive programming. It strengthens your control over spacing, alignment, and loop logic.

---

