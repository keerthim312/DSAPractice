# 🧩 Problem Statement

You are given an integer `N`. Write a **recursive function** to return the **sum of the first `N` natural numbers**.

---

## 🧠 Understanding Recursion

**Recursion** is a technique where a function calls itself to solve smaller parts of a problem.

In this problem, you can express the sum as:
sum(N) = N + sum(N-1)

### 🛑 Base Case:
If `N == 1`, the function should return `1`.

### 🔁 Recursive Case:
Add `N` to the result of the recursive call `sum(N - 1)`.

---

## ✅ Approach:  Recursive Sum Function

### 🔍 Intuition

Each time we call the function, we reduce `N` by 1, and add it to the result of the next recursive call. This continues until we reach `N = 1`.


### 📦 Python Code

```python
def NnumbersSum(self, N):
        # Base case
        if N == 1:
            return 1
        # Recursive case
        else:
            return N + self.NnumbersSum(N - 1)

```
---

#### Sample Input:
n = 4

#### Sample Output:
10

---

### Complexity Analysis:
**Time Complexity:** O(N)
Each call reduces N by 1, so there are N recursive calls.

**Space Complexity:** O(N)
Due to the recursion stack used in each call.

---

### Recursive Tree:
```
NnumbersSum(4)
    ↳ 4 + NnumbersSum(3)
              ↳ 3 + NnumbersSum(2)
                        ↳ 2 + NnumbersSum(1)
                                  ↳ 1
Final sum = 4 + 3 + 2 + 1 = 10

```
---

This approach elegantly computes the sum of natural numbers using the power of recursion.

---
