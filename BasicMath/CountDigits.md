# Count All Digits of a Number

## Approach:
[Simple while loop to count the number of digits]

---

### 1. Simple While Loop

#### Intuition:
To count the number of digits in a given number `n`, we repeatedly divide the number by `10` until it becomes `0`. Each division effectively removes the last digit of the number. We count how many times this operation is performed — that count represents the total number of digits.

There is a special case for `n = 0`, where we should directly return `1`, since `0` has one digit.

---

### Python Code:
```python
class Solution:
    def countDigit(self, n: int) -> int:
        # Special case for 0
        if n == 0:
            return 1
        
        cnt = 0
        while n > 0:
            cnt += 1
            n = n // 10
        return cnt

```
---

#### Sample Input:
n = 4

#### Sample Output:
1

#### Explanation:
4 has only 1 digit

---

### Complexity Analysis:
**Time Complexity:** O(log₁₀ n)
The number is divided by 10 until it becomes 0, so the number of operations is proportional to the number of digits.
**Space Complexity:** O(1)
No extra space is used, just a counter variable.

---

This simple digit-counting problem is a great beginner exercise in using loops and understanding number manipulation.

---
