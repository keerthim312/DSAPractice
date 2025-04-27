#  Symmetric Hourglass Star Pattern

## Problem Statement

Write a function to generate a **symmetric hourglass (bow-tie shaped)** pattern using stars (`*`) and spaces, based on a given input `n`.

The pattern consists of:
- An **upper half** including the middle row
- A **mirrored lower half**
- Stars on both left and right sides of each row
- Spaces in between forming a triangle/hollow section

---

## Approach

1. Loop from `1` to `n` (inclusive) to generate the **upper half** of the pattern.
2. For each row `i`:
   - Print `i` stars on the left
   - Print `2 * (n - i)` spaces in the center
   - Print `i` stars on the right
3. Loop from `n - 1` down to `1` to generate the **lower half** of the pattern (mirrored).
4. Print a newline after every row.

---

## Python Code

```python
def symmetry(n: int):
    # Upper half including the middle row
    for i in range(1, n + 1):  # i from 1 to n
        # Print left stars
        for j in range(1, i + 1):
            print("*", end=" ")

        # Print middle spaces (2 * (n - i))
        for j in range(1, 2 * (n - i) + 1):
            print(" ", end="")

        # Print right stars
        for j in range(1, i + 1):
            print("*", end=" ")

        print()  # Move to next line

    # Lower half
    for i in range(n - 1, 0, -1):  # i from n-1 down to 1
        # Print left stars
        for j in range(1, i + 1):
            print("*", end=" ")

        # Print middle spaces
        for j in range(1, 2 * (n - i) + 1):
            print(" ", end="")

        # Print right stars
        for j in range(1, i + 1):
            print("*", end=" ")

        print()  # Move to next line

```
---

### Sample Input:
n = 3

### sample Output:
```

*         * 
* *     * * 
* * * * * * 
* *     * * 
*         * 

```

---

### Complexity Analysis:
**Time Complexity:** O(n²)
Each row contains up to 2n operations (stars + spaces).

**Space Complexity:** O(1)
No additional data structures are used.

---
### Learning Outcomes:
 
Practice with nested loops and mirrored logic

Learn to control spacing and symmetry in 2D patterns

Strengthen skills in loop counters and ASCII art

---

