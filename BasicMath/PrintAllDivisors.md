# Divisors of a Number

## Problem Statement:
You are given an integer `n`. You need to find all the divisors of `n`. Return all the divisors of `n` as an array or list in sorted order.

### Definition:
A **divisor** of a number `n` is any number that divides `n` without leaving a remainder. For example:
- Divisors of `6` are `1, 2, 3, 6`.
- Divisors of `12` are `1, 2, 3, 4, 6, 12`.

---

## Approach:
We'll cover two approaches:
1. **Brute Force** – Check all numbers from `1` to `n` to see if they are divisors.
2. **Optimal** – Check only up to `sqrt(n)` for divisors to reduce unnecessary checks.

---

## 1. Brute Force Using a Loop

### Intuition:
We simply loop through all integers from `1` to `n` and check if each number divides `n` without a remainder.

### Python Code:
```python
class Solution:
    def divisors(self, n):
        divisors = []
        for i in range(1, n + 1):
            if n % i == 0:
                divisors.append(i)
        return divisors

```
---

### Complexity Analysis:
**Time Complexity:** O(n)
We check all integers from 1 to n, making the time complexity linear in terms of the input size.
**Space Complexity:** O(n)
We store the divisors in a list, so the space complexity is proportional to the number of divisors.

---

## 2. Optimal Solution Using Square Root

### Intuition:
Instead of checking all integers from 1 to n, we only need to check up to sqrt(n) because divisors come in pairs. For example, if i divides n, then n/i is also a divisor.
### Python Code:
```python
import math

class Solution:
    def divisors(self, n):
        divisors = []
        for i in range(1, int(math.sqrt(n)) + 1):
            if n % i == 0:
                divisors.append(i)
                if i != n // i:
                    divisors.append(n // i)
        return sorted(divisors)

```
---

#### Sample Input:
n = 6

#### Sample Output:
[1, 2, 3, 6]

#### Explanation:
Divisors of 6 are 1, 2, 3, 6

---

### Complexity Analysis:
**Time Complexity:** O(√n)
n the optimal approach, we loop from 1 to sqrt(n). For each integer i in this range, we check if i divides n. If i divides n, both i and n/i are divisors, and we append them to the list of divisors.

Since we loop only up to the square root of n, the number of iterations is approximately √n. This makes the time complexity O(√n).

Why O(√n)?
Divisors of a number come in pairs. For example, if i divides n, then n/i is also a divisor. We only need to check numbers up to sqrt(n) because for every divisor i, we automatically get the paired divisor n/i.
**Space Complexity:**  O(√n)
We store the divisors in a list. In the worst case, the number of divisors is proportional to the number of divisors that can be found within the range up to √n. Thus, the space complexity is also O(√n).

Why O(√n)?
The list of divisors stores all the divisors of n, but because divisors come in pairs (i.e., if i is a divisor, so is n/i), the list will have approximately 2 divisors for each divisor less than √n. Hence, the space complexity is proportional to √n.

---

Brute Force Approach is simple but inefficient for large numbers, as it checks all integers from 1 to n.

Optimal Approach improves the time complexity by checking only up to sqrt(n), making it much faster for larger inputs.

---
