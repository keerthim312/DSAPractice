# Reverse Triangle Star Pattern Problem

## Approach:
[Simple Nested Loop for reverse triangle star pattern]

---

### 1. Simple Nested Loop

#### Intuition:
This pattern printing problem generates a reverse right-angled triangle made of stars (`*`).  
The number of stars in each row decreases as we go down the rows.

The outer loop runs from 1 to n (to control the number of rows).  
The inner loop runs from 1 to n - i + 1 (to print decreasing stars as i increases).  
After printing the stars in one row, a newline character is printed to move to the next row.

This is a great pattern for understanding how the loop bounds affect the shape of the printed pattern.

---

#### Python Code:
```python
def seeding(n: int) -> None:
    # Print reverse triangle star pattern
    for i in range(1, n + 1):
        for j in range(1, n - i + 2):  # n - i + 1 times
            print("* ", end="")  # Print star with space
        print()  # Move to next line after each row
```
---

### Sample Input:
n = 5

### sample Output:
```
* * * * * 
* * * * 
* * * 
* * 
* 
```

---

### Complexity Analysis:
**Time Complexity:** O(n²)
Outer loop runs n times
Inner loop runs from n to 1, decreasing each time → total operations ≈ O(n²)
**Space Complexity:** O(1)
No additional space used beyond loop variables.

---

This reverse triangle star pattern helps reinforce loop control and is a common beginner-level problem for mastering nested loops.

---
