# Greatest Common Divisor (GCD) of Two Numbers

## Problem Statement:
You are given two integers `n1` and `n2`. You need to find the **Greatest Common Divisor (GCD)** of the two given numbers. Return the GCD of the two numbers.

---

## Approach:
We'll cover two approaches:
1. **Brute Force** – Check all possible divisors from high to low.
2. **Optimal** – Use the mathematical property: `GCD(a, b) = GCD(b, a % b)`.

---

## 1. Brute Force Using a Loop

### Intuition:
Start checking from the smaller of the two numbers, and go downward to find the largest number that divides both numbers.

### Python Code:
```python
class Solution:
    def GCD(self, n1: int, n2: int) -> int:
        for i in range(min(n1, n2), 0, -1):
            if n1 % i == 0 and n2 % i == 0:
                return i

```
---

### Complexity Analysis:
**Time Complexity:** O(min(n1, n2))
he loop runs from the smaller of n1 and n2 down to 1. In the worst case, this means iterating through all numbers from 1 to min(n1, n2).
**Space Complexity:** O(1)
We only use a few integer variables for iteration and checking divisibility, so no extra space is required.

---

## 2. Optimal Solution

### Intuition:
This algorithm is based on the fact that: GCD(a, b) = GCD(b, a % b)

### Python Code:
```python
class Solution:
    def GCD(self, n1: int, n2: int) -> int:
        while n2 != 0:
            n1, n2 = n2, n1 % n2
        return n1

```
---

#### Sample Input:
n1 = 4 and n2 = 6

#### Sample Output:
2

#### Explanation:
Divisors of 4 = [1, 2, 4], Divisors of 6 = [1, 2, 3, 6]

---

### Complexity Analysis:
**Time Complexity:** O(log(min(n1, n2)))
In each iteration, the size of one of the numbers reduces substantially, so the algorithm runs in logarithmic time relative to the smaller number. This makes it much more efficient than the brute force approach.
**Space Complexity:** O(1)
Only a constant amount of extra space is used for storing the two numbers (n1 and n2), regardless of the input size.

---

The Brute Force approach is easier to understand but inefficient, especially for large numbers.

The Optimal solution is more efficient, running in logarithmic time, and is widely used in practical applications for computing the GCD.

---
