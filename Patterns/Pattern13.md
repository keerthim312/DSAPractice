# Reverse N Letter Triangle Pattern

## Problem Statement

Generate a **Reverse N Letter Triangle** for a given integer n.  
Each row contains:
- Sequential uppercase letters starting from 'A'
- The number of letters decreases with each row

This forms an **inverted right-angled triangle** of letters.

---

## Approach

To create the reverse letter triangle:
1. Loop through each row i from n down to 1.
2. For each row:
   - Print the first i letters starting from 'A'.
   - Use the chr(ord('A') + j) to get each character.
3. Move to the next line after printing each row.

---

## Python Code

```python
def nLetterTriangle(n: int):
    for i in range(n, 0, -1):
        for j in range(i):
            print(chr(ord("A") + j), end = " ")
        print()

```
---

### Sample Input:
n = 4

### sample Output:
```
1 
2 3 
4 5 6 
7 8 9 10 

```

---

### Complexity Analysis:
**Time Complexity:** O(n²)
Each row prints i numbers, with total numbers printed equal to n(n + 1)/2.

**Space Complexity:** O(1)
Only loop variables and a counter are used.

---
### Learning Outcomes:

Practice with nested loops and number patterns.

Learn how to use a counter variable across nested loops.

Understand how to build incremental triangular patterns using loop control.

---

