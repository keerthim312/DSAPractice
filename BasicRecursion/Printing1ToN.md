# 🚀 Print Numbers from 1 to N Using Recursion

## 🧩 Problem Statement:
You are given an integer `n`. You need to print all numbers from **1 to `n`** using **recursion**.  
You must not use loops (`for`, `while`, etc.). Only recursion is allowed.

---

## 🧠 Definition:
**Recursion** is a method where a function calls itself to solve smaller subproblems until it reaches a base case that stops the process.

---

## ✅ Approach 1: Forward Recursion

### 🔍 Intuition:
We start from `1` and go up to `n`. Each function call prints the current number and recurses with the next number (`i + 1`) until the base condition `i > n` is met.

---

### 📦 Python Code:
```python
def print_1_to_n(i, n):
    if i > n:
        return
    print(i)
    print_1_to_n(i + 1, n)

# Driver code
n = int(input("Enter a number: "))
print_1_to_n(1, n)

```
---

#### Sample Input:
n = 5

#### Sample Output:
```
1
2
3
4
5
```

---

## ✅ Approach 2: Backward Recursion (Using Backtracking)

### 🔍 Intuition:
Start from n and go down to 1. But instead of printing first, call the function recursively and then print during the unwinding of the recursion. This prints in ascending order.

---

### 📦 Python Code:
```python
def print_1_to_n_backtrack(i, n):
    if i < 1:
        return
    print_1_to_n_backtrack(i - 1, n)
    print(i)

# Driver code
n = int(input("Enter a number: "))
print_1_to_n_backtrack(n, n)

```
---

#### Sample Input:
n = 5

#### Sample Output:
```
1
2
3
4
5
```

---

### Complexity Analysis:
**Time Complexity:** O(n)
One recursive call per number.

**Space Complexity:** O(n)
Due to recursion stack.

---

Both forward and backward recursion techniques can solve the problem, but the key difference lies in when you print — before or after the recursive call.

---
