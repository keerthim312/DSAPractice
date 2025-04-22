# Triangle Number Pattern Problem

## Approach:
[Simple Nested Loop for Number Triangle Pattern]

---

### 1. Simple Nested Loop

#### Intuition:
This pattern printing problem creates a right-angled triangle of numbers.  
Each row i contains the number i, printed i times.

The outer loop runs from 1 to n (inclusive) to handle each row.  
The inner loop runs from 1 to i for printing the current row's number repeatedly.  
After printing one row, a line break is added to start the next row.

This is a foundational exercise in learning nested loops and number-based pattern generation.

---

#### Python Code:
```python
def triangle(n: int) -> None:
    # Print triangle number pattern
    for i in range(1, n + 1):
        for j in range(1, i + 1):
            print(i, end=" ")  # Print current row number
        print()  # Move to the next line after each row
```
---
#### Sample Input:
n = 5

#### Sample Output:
```
1
2 2
3 3 3
4 4 4 4
5 5 5 5 5
```
---

### Complexity Analysis:
**Time Complexity:** O(n²)
Two nested loops; the outer runs n times, and the inner runs i times for each row (1 + 2 + ... + n = O(n²)).
**Space Complexity:** O(1)
No extra space is used except for loop variables.

---

This number triangle pattern is perfect for beginners to get hands-on experience with nested loops and pattern logic.

---



