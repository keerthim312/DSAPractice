# Reverse Triangle Number Pattern Problem

## Approach:
[Simple Nested Loop for reverse triangle number pattern]

---

### 1. Simple Nested Loop

#### Intuition:
This pattern printing problem generates a triangle of decreasing length, where each row prints ascending numbers starting from 1.  
The number of elements in each row decreases as the row number increases.

- The outer loop runs from 1 to n(controls the number of rows).
- The inner loop runs from 1 to n - i + 1 (controls how many numbers to print in each row).
- Each inner loop prints numbers in ascending order from 1 up to the decreasing limit.
- After each row, a newline is printed to start a new row.

This pattern helps learners understand variable loop bounds and dynamic printing.

---

#### Python Code:
```python
def nNumberTriangle(n: int) -> None:
    # Print reverse triangle number pattern
    for i in range(1, n + 1):
        for j in range(1, n - i + 2):  # Print numbers from 1 to n - i + 1
            print(j, end=" ")
        print()  # Move to next line after each row
```
---

### Sample Input:
n = 5

### sample Output:
```
1 2 3 4 5 
1 2 3 4 
1 2 3 
1 2 
1 

```

---

### Complexity Analysis:
**Time Complexity:** O(n²)
Outer loop runs n times
Inner loop decreases in length each time, with total operations ≈ O(n²)
**Space Complexity:** O(1)
No additional space used beyond loop variables.

---

This number-based reverse triangle pattern is a great way to practice variable loop ranges and nested loop logic.

---

