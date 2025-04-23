# Star Diamond Pattern Problem

## Approach:
[Creating a Diamond Shape using Nested Loops]

---

### 1. Simple Nested Loop for Star Diamond

#### Intuition:
This pattern prints a **diamond shape** of stars (`*`), where:
- The **upper half** forms an increasing pyramid of stars.
- The **lower half** is a mirror image of the upper half, but the star count decreases.

- The outer loop runs twice:
  - The first loop prints the **upper half**, starting with one star and increasing each row.
  - The second loop prints the **lower half**, starting with a wide base of stars and decreasing each row.

Each row consists of:
- **Spaces** on the left to center the stars.
- **Stars** in the middle.

---

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
n = 3

### sample Output:
```
  *  
 *** 
*****
 *** 
  *  

```

---

### Complexity Analysis:
**Time Complexity:** O(n²)
The outer loop runs n times for the upper half and n-1 times for the lower half.
Each loop iteration involves string concatenation (spaces + stars).
**Space Complexity:** O(1)
No additional space is used beyond loop counters and string operations.

---
This diamond pattern is a classic example for:

Learning how to adjust spaces dynamically.

Handling symmetry in patterns.

Practicing loop nesting and range management.

---

