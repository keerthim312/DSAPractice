# Prime Number Check

## Problem Statement:
You are given an integer `n`. You need to check if the number is a prime number or not. Return `true` if it is a prime number, otherwise return `false`.

### Definition:
A **prime number** is a number greater than 1 that has no divisors except `1` and itself. For example:
- `5` is a prime number because its divisors are only `1` and `5`.
- `6` is not a prime number because its divisors are `1`, `2`, `3`, and `6`.

---

## Approach:
We'll cover two approaches:
1. **Brute Force** – Check divisibility for all numbers from `1` to `n`.
2. **Optimal** – Check divisibility only up to `sqrt(n)` for efficiency.

---

## 1. Brute Force Using a Loop

### Intuition:
Check all numbers from `2` to `n-1`. If `n` is divisible by any of these numbers, it's not prime. If no such number divides `n`, it is prime.

### Python Code:
```python
class Solution:
    def isPrime(self, n: int) -> bool:
        if n <= 1:
            return False
        for i in range(2, n):
            if n % i == 0:
                return False
        return True

```
---

### Complexity Analysis:
**Time Complexity:** O(n)
We check all numbers from 2 to n-1 to see if any divide n, which takes linear time in the size of n.
**Space Complexity:** O(1)
We only use a few integer variables for iteration and checking divisibility, so no extra space is required.

---

## 2. Optimal Solution Using Square Root

### Intuition:
Instead of checking all numbers up to n-1, we only need to check up to sqrt(n) because any factor larger than sqrt(n) would have already been found as the corresponding smaller factor.
### Python Code:
```python
import math
class Solution:
    def isPrime(self, n: int) -> bool:
        if n <= 1:
            return False
        for i in range(2, int(math.sqrt(n)) + 1):
            if n % i == 0:
                return False
        return True

```
---

#### Sample Input:
n = 5

#### Sample Output:
True
#### Explanation:
Divisors of 6 are 1, 2, 3, 6

---

### Complexity Analysis:
**Time Complexity:** O(sqrt(n))
The loop runs only up to sqrt(n) instead of n, which reduces the number of iterations, especially for large values of n.
**Space Complexity:**  O(1)
We only use a few integer variables and don't require extra space that grows with the input size.

---

Brute Force Approach checks all numbers from 2 to n-1 and has a time complexity of O(n).

Optimal Approach improves the time complexity to O(sqrt(n)) by only checking divisibility up to sqrt(n).

The optimal solution is much more efficient for larger numbers.

---
