# Square Star Pattern Problem

## Approach:
[Simple Nested Loop for square star pattern]

---

### 1. Simple Nested Loop

#### Intuition:
This pattern printing problem uses two nested loops to display a square made of stars.
The outer loop runs n times (for the number of rows), and the inner loop also runs n times (for the number of columns).  
On each iteration of the inner loop, we print a * followed by a space (`* `), and after completing one row, we move to the next line.
This is a fundamental example for understanding how nested loops work in pattern problems.

---

#### Python Code:
```python
def nForest(n: int) -> None:
    # Print n x n star pattern
    for i in range(n):
        for j in range(n):
            print("* ", end="")  # Print star with space
        print("\n", end="")      # Move to next line after each row
```
---

#### Sample Input:
n = 4

#### Sample Output:
* * * * 
* * * * 
* * * * 
* * * *

---

### Complexity Analysis:
**Time Complexity:** O(n²)
Two nested loops each run n times.
**Space Complexity:** O(1)
We use no extra space except for loop variables.

---

This basic star pattern problem is a great starting point for beginners learning loops and pattern construction. 

---

