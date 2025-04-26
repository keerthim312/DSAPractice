# Alpha Hill Pattern

## Problem Statement

Generate an **Alpha Hill** pattern for a given integer `n`.

Each row contains:
- Increasing sequence of uppercase alphabets starting from 'A'
- Then a decreasing sequence of alphabets creating a palindromic hill
- The output is shaped as a symmetrical triangle (hill) using letters

---

## Approach

To create the Alpha Hill pattern:

1. Loop through each row `i` from 1 to `n`.
2. For each row:
   - Print `(n - i)` leading spaces (each as two spaces for visual alignment).
   - Print increasing letters from 'A' up to the `i`-th character.
   - Then print decreasing letters back down to 'A'.
3. Move to the next line after each row.

---

## Python Code

```python
def alphaHill(n: int):
    for i in range(1, n + 1):
        # Print leading spaces using a loop
        for j in range(1, n - i + 1):
            print("  ", end="")  # Two spaces for alignment

        # Print increasing letters
        for j in range(1, i + 1):
            print(chr(ord('A') + j - 1), end=" ")

        # Print decreasing letters
        for j in range(i - 1, 0, -1):
            print(chr(ord('A') + j - 1), end=" ")

        print()  # Newline after each row

```
---

### Sample Input:
n = 4

### sample Output:
```
      A
    A B A
  A B C B A
A B C D C B A

```

---

### Complexity Analysis:
**Time Complexity:** O(n²)
Each row prints up to 2i - 1 characters, giving a total of approximately n² operations.
**Space Complexity:** O(1)
No extra space used aside from loop variables.

---
### Learning Outcomes:
Learn to generate symmetrical (palindromic) letter patterns.

Improve loop control for constructing mirrored sequences.

Practice ASCII character manipulations using ord() and chr() functions.

---

