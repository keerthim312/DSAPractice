# Print Name N Times Using Recursion

## 🧩 Problem Statement:
You are given an integer `n`. You need to print your name exactly `n` times using **recursion**.  
You must not use any loops — only recursion.

---

## 🧠 Prerequisite:
- Understand how to define functions with parameters.
- Familiarity with recursion, base cases, and the concept of recursive calls.

---

## 🧠 Concept:
Since we cannot use a loop to count how many times the name has been printed, we will pass a counter variable `i` as a parameter to the recursive function.

We start with `i = 1` and:
- Print the name,
- Call the function again with `i + 1`,
- Stop when `i > n` (base case).

---

## 🔍 Approach:
1. Define a function that takes two parameters: the current count `i` and the target number `n`.
2. Print the name in each call.
3. Terminate the recursion when `i` exceeds `n`.

---

## 💻 Python Code:
```python
def print_name(i, n):
    # Base Condition
    if i > n:
        return

    # Print the name
    print("Raj")

    # Recursive Call
    print_name(i + 1, n)

# Driver Code
n = int(input("Enter the number of times to print your name: "))
print_name(1, n)

```
---

#### Sample Input:
n = 3

#### Sample Output:
```
Raj
Raj 
Raj
```

---


### Recursive Tree:
```
print_name(1, 3)
    → Raj
    → print_name(2, 3)
        → Raj
        → print_name(3, 3)
            → Raj
            → print_name(4, 3)
                → return
```

---

### Complexity Analysis:
**Time Complexity:** O(n)
We make n recursive calls, and each call takes constant time (printing the name once).
**Space Complexity:** O(n)
The recursion stack holds n frames, and each frame stores the state of a function call.

---

This problem is a foundational step in learning how recursion works with parameters and base conditions.

---
