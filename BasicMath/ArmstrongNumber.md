# Armstrong Number Check

## Problem Statement:
You are given an integer `n`. You need to check whether it is an **Armstrong number** or not. Return `True` if it is an Armstrong number, otherwise return `False`.

### Definition:
An **Armstrong number** (also known as a **narcissistic number**) is a number that is equal to the sum of its own digits each raised to the power of the number of digits. For example:
- **153** is an Armstrong number because:
  - Number of digits = 3
  - `1^3 + 5^3 + 3^3 = 1 + 125 + 27 = 153`
- **12** is **not** an Armstrong number because:
  - Number of digits = 2
  - `1^2 + 2^2 = 1 + 4 = 5`

---

## Approach:

### 1. Brute Force Approach

#### Intuition:
The approach involves checking if the number is equal to the sum of its digits raised to the power of the number of digits in the number.

#### Python Code:
```python
class Solution:
    def isArmstrong(self, n):
        num = n  # Store the original number
        k = len(str(n))  # Number of digits
        sum_of_powers = 0  # Initialize the sum of digits raised to the power
        while n > 0:
            ld = n % 10  # Extract last digit
            sum_of_powers += ld ** k  # Add the digit raised to the power
            n = n // 10  # Remove last digit
        return sum_of_powers == num  # Check if sum of powers equals the original number

```
---

#### Sample Input:
n = 153

#### Sample Output:
True

#### Explanation:
`1^3 + 5^3 + 3^3 = 1 + 125 + 27 = 153`

---

### Complexity Analysis:
**Time Complexity:** O(d)
Where d is the number of digits in n. This is because we are iterating over each digit of n to compute the sum of powers.
**Space Complexity:** O(1)
We only use a few extra variables (e.g., num, sum_of_powers, k), so the space complexity is constant.

---

This is a simple implementation to check if a number is an Armstrong number by using basic mathematical operations such as modulo and exponentiation. The method works efficiently for all integers within the given constraints.

---
