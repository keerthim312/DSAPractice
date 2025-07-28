# 🧩 LeetCode 509: Fibonacci Number

## 🧩 Problem Statement

The Fibonacci numbers, commonly denoted F(n) form a sequence, called the Fibonacci sequence, such that each number is the sum of the two preceding ones, starting from 0 and 1. 

That is,
F(0) = 0, F(1) = 1
F(n) = F(n - 1) + F(n - 2), for n > 1.

Given n, calculate F(n).

---

## 🧠 Understanding Recursion

Recursion is a programming technique where a function calls itself to solve smaller instances of the same problem. In the case of the Fibonacci sequence, each number is the sum of the two preceding ones, starting from 0 and 1.

The Fibonacci sequence is defined as:

F(0) = 0
F(1) = 1
F(n) = F(n - 1) + F(n - 2) for n > 1

---

## ✅ Approach: Recursive Approach

### 🔍 Intuition

Each time we call the function, we reduce n by 1 or 2, and add the results of the recursive calls. This continues until we reach the base cases (n == 0 or n == 1).

### 📦 Python Code

```python
class Solution:
    def fib(self, n: int) -> int:
        if n <= 1:
            return n
        return self.fib(n - 1) + self.fib(n - 2)

```
---

#### Sample Input:
n = 4

#### Sample Output:
3

#### Explanation: 

F(4) = F(3) + F(2) = 2 + 1 = 3.

---

### Complexity Analysis:
**Time Complexity:** O(2^n)

Each call to fib(n) generates two additional calls, leading to an exponential growth in the number of function calls.

**Space Complexity:** O(N)

The maximum depth of the recursion stack is proportional to n.

---

### Recursive Tree:
```
fib(4)
  ↳ fib(3)
        ↳ fib(2)
              ↳ fib(1) → 1
              ↳ fib(0) → 0
        ↳ fib(1) → 1
  ↳ fib(2)
        ↳ fib(1) → 1
        ↳ fib(0) → 0

```
---

This recursive approach elegantly computes the nth Fibonacci number by breaking down the problem into smaller subproblems. While the naive recursive method is intuitive, it becomes inefficient for larger n due to redundant calculations. Implementing memoization significantly enhances performance by storing and reusing previously computed results.

---
