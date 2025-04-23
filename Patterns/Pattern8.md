# Inverted Centered Star Triangle Pattern Problem

## Approach:
[Centered Downward Pyramid using Nested Loops]

---

### 1. Simple Nested Loop for Inverted Star Triangle

#### Intuition:
This pattern prints an **inverted pyramid** made of stars (`*`), where each row contains an **odd number of stars**, decreasing as the row number increases. The stars are centered by adding spaces on both sides.

- The outer loop runs from `1` to `n` (controls number of rows).
- Each row consists of:
  - **Left spaces**: `i - 1` spaces
  - **Stars**: `2 * (n - i) + 1` stars
  - **Right spaces**: `i` spaces (optional for symmetry)

This structure creates a downward-pointing centered triangle.

---

#### Python Code:
```python
def nStarTriangle(n: int) -> None:
    for i in range(1, n + 1):
        # Print left spaces
        for j in range(1, i):
            print(" ", end="")
        
        # Print stars
        for j in range(1, 2 * (n + 1) - 2 * i):
            print("*", end="")
        
        # Optional: Print right spaces for symmetry
        for j in range(1, i + 1):
            print(" ", end="")

        # Move to the next line
        print()
```
---

### Sample Input:
n = 3

### sample Output:
```
*****
 *** 
  *  

```

---

### Complexity Analysis:
**Time Complexity:** O(n²)
Outer loop runs n times.
Inner loops print spaces and stars with total operations ~ 2n per row.

**Space Complexity:** O(1)
No extra space used beyond loop counters.

---

This inverted centered triangle is a great practice pattern for learning how to:

Dynamically adjust space and character count

Handle centered alignment

Work with decreasing sequences

---

