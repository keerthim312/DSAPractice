# Alpha Ramp Pattern

## Problem Statement

Generate an **Alpha Ramp** pattern for a given integer `n`.

Each row contains:
- Repeated uppercase letters.
- The letter in row `i` is the `(i+1)`-th letter of the English alphabet.
- This forms a right-angled triangle where each row contains the same letter repeated.

---

## Approach

To generate the Alpha Ramp pattern:

1. Loop through each row `i` from `0` to `n - 1`.
2. For each row:
   - Print the `(i+1)`-th alphabet letter, repeated `(i+1)` times.
   - Use `chr(ord('A') + i)` to get the appropriate character.

---

## Python Code

```python
def alphaRamp(n: int) -> None:
    for i in range(n):
        for j in range(i + 1):
            print(chr(ord('A') + i), end=" ")
        print()

```
---

### Sample Input:
n = 4

### sample Output:
```
A 
B B 
C C C 
D D D D 


```

---

### Complexity Analysis:
**Time Complexity:** O(n²)
Total letters printed: 1 + 2 + 3 + ... + n = n(n + 1)/2.

**Space Complexity:** O(1)
No extra space is used apart from loop variables.

---
### Learning Outcomes:
Understand character generation with ASCII operations using ord() and chr().

Practice nested loop control to produce letter-based patterns.

Strengthen understanding of pattern logic for rows and character repetition.

---
