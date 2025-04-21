# Number Triangle Pattern Problem

## Approach:
[Simple Nested Loop with Incrementing Numbers]

---

### 1. Simple Nested Loop with Incrementing Numbers

#### Intuition:
This pattern printing problem uses two nested loops to display a right-angled triangle of incrementing numbers.  
The outer loop controls the number of rows (from 1 to n), and the inner loop prints numbers from 1 up to the current row number.  
After printing each row, we move to the next line.

This is a classic pattern that helps build a solid understanding of loop control and number handling in patterns.

---

#### Python Code:
```python
def nTriangle(n: int) -> None:
    # Print a triangle where each row contains increasing numbers starting from 1
    for i in range(1, n + 1):
        for j in range(1, i + 1):
            print(j, end=" ")  # Print number with space
        print()  # Move to next line after each row
```

---

#### Sample Input:
n = 4

#### Sample Output:
1
1 2
1 2 3
1 2 3 4

### Complexity Analysis:
**Time Complexity:** O(n²)
Two nested loops where the inner loop runs i times for each i from 1 to n.
**Space Complexity:** O(1)
Constant space used, apart from loop variables.

---

This number triangle is a great way to practice basic nested loop patterns.

---
