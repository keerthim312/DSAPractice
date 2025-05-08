# 🧩 Problem Statement

Given a number X,  print its factorial.

To obtain the factorial of a number, it has to be multiplied by all the whole numbers preceding it. More precisely X! = X*(X-1)*(X-2) … 1.

Note: X  is always a positive number. 

---

## 🧠 Understanding Factorial

The **factorial** of a non-negative integer `N` is the product of all positive integers less than or equal to `N`. 

Formally:
- `N! = N * (N-1) * (N-2) * ... * 1` for `N > 0`
- `0! = 1` (base case)

For example:
- `5! = 5 * 4 * 3 * 2 * 1 = 120`
- `3! = 3 * 2 * 1 = 6`

---

## ✅ Approach:

To compute the factorial of a number N using recursion, we break down the problem into smaller subproblems based on the mathematical definition of factorial:
N! = N × (N-1)!
with a base case: 0! = 1

## 🧑‍💻 Python Code: 

```python
def fact(n):
    if n == 0:
        return 1
    return n * fact(n - 1)

def main():
    n = 5
    ans = fact(n)
    print(ans)

main()

```
---

#### Sample Input:
n = 5

#### Sample Output:
120

---

### Complexity Analysis:
**Time Complexity:** O(N)
One recursive call per value from n down to 0.

**Space Complexity:** O(N)
Each recursive call adds one frame to the call stack until the base case is reached.

---

### Recursive Tree:
```
factorial(3)
    ↳ 3 * factorial(2)
              ↳ 2 * factorial(1)
                        ↳ 1 * factorial(0)
                                  ↳ 1
Final result = 3 * 2 * 1 = 6

```
---

Recursion provides a direct and elegant solution for calculating factorials, closely mirroring their mathematical definition and helping build a solid foundation in recursive thinking.

---
