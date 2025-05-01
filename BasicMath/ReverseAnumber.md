# Reverse a Number

## Approach:
[Simple while loop to reverse digits of the number]

---

### 1. Simple While Loop

#### Intuition:
To reverse a number `n`, we extract its digits one by one using the modulo operator (`% 10`), and construct the reversed number by multiplying the current reversed number by `10` and adding the new digit. We continue this until all digits are processed (i.e., `n` becomes 0).

This technique works well for any non-negative integer and handles the reversal without converting to a string.

---

### Python Code:
```python
class Solution:
    def reverseNumber(self, n: int) -> int:
        reversedNumber = 0
        while n > 0:
            ld = n % 10
            reversedNumber = (reversedNumber * 10) + ld
            n = n // 10
        return reversedNumber

```
---

#### Sample Input:
n = 25

#### Sample Output:
52

#### Explanation:
Digits reversed: 5,2 → 52

---

### Complexity Analysis:
**Time Complexity:** O(log₁₀ n)
Each operation removes one digit from the number, so total steps equal number of digits.
**Space Complexity:** O(1)
Only a few integer variables are used for computation.

---

This is a classic number manipulation problem for beginners and helps practice using loops and arithmetic operations.

---
