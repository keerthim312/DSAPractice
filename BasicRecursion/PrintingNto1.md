# 🧩 Problem Statement

You are given an integer `n`. Write a recursive function to print all numbers from **`n` to 1**, without using loops (`for`, `while`, etc.).

---

## 🧠 Understanding Recursion

**Recursion** is a technique where a function calls itself to solve smaller instances of the same problem. It typically involves:

- **Base Case**: The condition under which the recursion stops.
- **Recursive Case**: The part where the function calls itself with modified parameters.

---

## ✅ Approach: Forward Recursion

### 🔍 Intuition

Start from `n` and print the current number. Then, recursively call the function with `n-1` until `n` becomes less than 1.

### 📦 Python Code

```python
def print_n_to_1(n):
    if n < 1:
        return
    print(n)
    print_n_to_1(n - 1)

# Driver code
n = int(input("Enter a number: "))
print_n_to_1(n)

```
---

#### Sample Input:
n = 5

#### Sample Output:
```
5
4
3
2
1
```

---

## ✅ Approach 2: Backward Recursion 

### 🔍 Intuition:
Start from 1 and recursively call the function until n is reached. Then, print the current number during the "unwinding" phase of recursion

---

### 📦 Python Code:
```python
def print_1_to_n_backtrack(i, n):
    if i > n:
        return
    print_1_to_n_backtrack(i + 1, n)
    print(i)

# Driver code
n = int(input("Enter a number: "))
print_1_to_n_backtrack(1, n)

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

### Tree Representation:

#### Forward Recursion: 
```
print_n_to_1(n)
    |
    v
print_n_to_1(n-1)
    |
    v
print_n_to_1(n-2)
    |
    v
...
    |
    v
print_n_to_1(1)

```

#### Back Recursion:
```
print_1_to_n_backtrack(1, n)
    |
    v
print_1_to_n_backtrack(2, n)
    |
    v
print_1_to_n_backtrack(3, n)
    |
    v
...
    |
    v
print_1_to_n_backtrack(n, n)

```

---

Both forward and backward recursion approaches effectively print numbers from n to 1. The choice between them depends on whether you prefer to print during the recursive calls (forward) or during the return phase (backward).

---
