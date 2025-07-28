# 🔢 Bubble Sort

## 🧠 Problem Statement:

Given an array of `N` integers, implement the **Bubble Sort** algorithm to sort the array in **non-decreasing order**.

### Definition:
A sorted array in **non-decreasing** order is one in which each element is **greater than or equal to** the one before it.

Examples:
- `[1, 2, 3, 4]` is non-decreasing ✅  
- `[3, 2, 1]` is not non-decreasing ❌

---

## ✅ Approach:
We'll look at two approaches:
1. **Brute Force** – Using Python’s built-in sort method.
2. **Optimal** – Manual implementation using the Bubble Sort algorithm.

---

## 1. Brute Force Using Built-in Sort

### 🔍 Intuition:
Use Python’s inbuilt sorting function, which is highly optimized internally (Timsort).

### 🧾 Python Code:
```python
class Solution:
    def sortArray(self, nums: list[int]) -> list[int]:
        nums.sort()
        return nums
```

---

### 📊 Complexity Analysis:
- **Time Complexity:** O(n log n)  
  Python’s built-in sort uses Timsort which performs in n log n time.
- **Space Complexity:** O(1)  
  In-place sort, uses constant extra space.

---

## 2. Optimal Approach: Bubble Sort

### 🔍 Intuition:
In each iteration, we push the largest unsorted element to the end by repeatedly swapping adjacent elements if they are in the wrong order.

### 🧾 Python Code:
```python
class Solution:
    def bubbleSort(self, nums: list[int]) -> list[int]:
        n = len(nums)
        for i in range(n - 1, 0, -1):
            for j in range(i):
                if nums[j] > nums[j + 1]:
                    nums[j], nums[j + 1] = nums[j + 1], nums[j]
        return nums
```

---

### 🧪 Sample Input:
```python
nums = [13, 46, 24, 52, 20, 9]
```

### ✅ Sample Output:
```python
[9, 13, 20, 24, 46, 52]
```

---

### 📊 Complexity Analysis:
- **Time Complexity:** O(n²)  
  - Worst & Average Case: O(n²)  
  - Best Case: O(n) (if optimized with an early-stop flag)
- **Space Complexity:** O(1)  
  In-place sorting.

---

## 📌 Summary:

| Approach    | Time Complexity | Space Complexity | Notes                                               |
| ----------- | --------------- | ---------------- | --------------------------------------------------- |
| Brute Force | O(n log n)      | O(1)             | Uses efficient built-in sort                        |
| Bubble Sort | O(n²)           | O(1)             | Easy to implement, not efficient for large datasets |

Bubble Sort is simple and great for learning, but inefficient for large arrays. Consider using built-in methods or advanced sorts like Merge/Quick Sort for large inputs.