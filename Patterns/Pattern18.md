# Alpha Triangle Pattern

## Problem Statement

Generate an **Alpha Triangle** pattern for a given integer `n`.

Each row contains:
- A decreasing sequence of uppercase alphabets.
- Each row starts from the `n`-th alphabet and goes backward.
- The number of letters in each row equals the row number.

This forms a right-angled triangle aligned to the left, with reverse alphabet rows.

---

## Approach

To generate the Alpha Triangle pattern:

1. Loop through each row `i` from `1` to `n`.
2. For each row:
   - Start from the `n`-th letter (`chr(ord('A') + n - 1)`).
   - Print `i` characters, decrementing the character each time.
3. Print a newline after each row.

---

## Python Code

```python
def alphaTriangle(n: int):
    for i in range(1, n + 1):  # 1-based rows
        start = ord('A') + n - 1  # Always start from 'A' + N - 1
        for j in range(1, i + 1):  # 1-based loop for characters
            print(chr(start - j + 1), end=" ")
        print()

```
---

### Sample Input:
n = 4

### sample Output:
```
D
D C
D C B
D C B A

```

---

### Complexity Analysis:
**Time Complexity:** O(n²)
Total characters printed = 1 + 2 + 3 + ... + n = n(n + 1)/2.

**Space Complexity:** O(1)
Only loop counters and character variables are used.

---
### Learning Outcomes:
Practice generating reverse alphabetical sequences.

Understand character manipulation using ASCII (ord and chr).

Gain confidence working with nested loops for triangular patterns.

---

