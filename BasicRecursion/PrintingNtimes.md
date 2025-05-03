# Introduction to Recursion – Understand Recursion by Printing Something N Times

## 🧩 Problem Statement:
You are given an integer `n`. You need to print a message or number exactly `n` times using **recursion**.  
Return nothing — simply print the message/number on each line.

### Note:
You are **not allowed to use loops** like `for` or `while`. The goal is to understand how recursion can replace iteration.

---

## 🧠 Definition:
**Recursion** is a technique where a function calls itself. It continues calling itself until a **base condition** is met that stops the recursion.

---

## Approach:
We will implement a recursive function that:
1. Accepts a counter `i` and a limit `n`.
2. Prints something (like "Hello" or the number `i`).
3. Recursively calls itself with `i + 1`.
4. Stops when `i > n` (base case).

---

## 1. Basic Recursion to Print N Times

### Intuition:
This example introduces how recursion works by using it to print a value multiple times — a basic stepping stone toward more complex recursive logic.

---

### Python Code:
```python
def print_n_times(i, n):
    # Base Condition
    if i > n:
        return

    # Print message or number
    print("Hello")  # or print(i) to print numbers from 1 to n

    # Recursive Call
    print_n_times(i + 1, n)

# Driver code
n = int(input("Enter a number: "))
print_n_times(1, n)

```
---

#### Sample Input:
n = 3

#### Sample Output:
```
Hello
Hello
Hello
```

---

### Complexity Analysis:
**Time Complexity:** O(n)
We make n recursive calls.
**Space Complexity:** O(n)
Each recursive call takes up stack space.

---

This problem helps build your foundation in recursion before moving on to tasks like factorial, Fibonacci, or backtracking.

---
