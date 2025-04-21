# Triangle Star Pattern Problem

## Approach:
[Simple Nested Loop for Right-Angled Triangle]
---
### 1. Simple Nested Loop for Right-Angled Triangle

#### Intuition:
This pattern printing problem uses two nested loops to display a right-angled triangle made of stars.
The outer loop runs n times (for the number of rows), and the inner loop runs a number of times corresponding to the row number.  
On each iteration of the inner loop, we print a * followed by a space (`* `), and after completing one row, we move to the next line.

This is a fundamental example for understanding how nested loops work in triangle pattern problems.

---

#### Python Code:
```python
def nForest(n: int) -> None:
    # Print right-angled triangle pattern
    for i in range(1, n + 1):
        for j in range(i):
            print("* ", end="")  # Print star with space
        print()  # Move to next line after each row
```
---

#### Sample Input:
n = 4

### Sample Output:
*
* * 
* * *
* * * *

---

### Complexity Analysis:
**Time Complexity:** O(n²)
Two nested loops, with the inner loop running i times where i is the current row number, resulting in an overall time complexity of O(n²).
**Space Complexity:** O(1)
We use no extra space except for loop variables.

---

This basic triangle star pattern problem is a great starting point for beginners learning loops and pattern construction.

---