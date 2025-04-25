# N Letter Triangle Pattern

## Problem Statement

Generate an **N Letter Triangle** for a given integer n.  
Each row contains:
- Sequential uppercase letters starting from 'A'
- Each row i prints the first i letters of the English alphabet

This forms a **right-angled triangle** of letters.

---

## Approach

To create the letter triangle pattern:
1. Loop through each row i from 1 to n.
2. For each row:
   - Use a nested loop to print i characters.
   - Start from the ASCII value of 'A' and increment using chr(ord("A") + j).

---

## Python Code

```python
def nLetterTriangle(n: int) -> None:
    for i in range(1, n + 1):
        for j in range(i):
            print(chr(ord("A") + j), end = " ")
        print()

```
---

### Sample Input:
n = 4

### sample Output:
```
A B C D 
A B C 
A B 
A 

```

---

### Complexity Analysis:
**Time Complexity:** O(n²)
Each row prints decreasing letters from n to 1 rows, with total operations equal to n(n + 1)/2.

**Space Complexity:** O(1)
Only loop counters are used.

---
### Learning Outcomes:
Practice using ASCII character manipulation in Python.

Understand how to implement reverse patterns using loops.

Develop fluency with nested loop control and character generation.

---

