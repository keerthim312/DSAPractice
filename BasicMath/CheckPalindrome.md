# Check if a Number is a Palindrome

## Approach:
[Reverse the number and compare it to the original]

---

### 1. Reverse and Compare

#### Intuition:
A number is a **palindrome** if it reads the same forward and backward. To check this, we reverse the number using a simple loop (digit-by-digit reversal) and then compare it to the original number. If both are equal, it’s a palindrome.

Negative numbers are not palindromes, as the negative sign doesn’t appear at the end when reversed.

---

### Python Code:
```python
class Solution:
    def isPalindrome(self, n: int) -> bool:
        if n < 0:
            return False       
        rev = 0
        dup = n
        while n > 0:
            ld = n % 10
            rev = (rev * 10) + ld
            n = n // 10        
        return rev == dup

```
---

#### Sample Input:
n = 121

#### Sample Output:
True

#### Explanation:
121 reversed is 121

---

### Complexity Analysis:
**Time Complexity:** O(log₁₀ n)
The number is processed digit by digit.
**Space Complexity:** O(1)
Only a few integer variables are used.

---

This problem helps practice number reversal and logical comparison, commonly asked in coding interviews.

---
