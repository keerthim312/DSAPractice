# 🔢 Selection Sort

## 🧠 Problem Statement:

You are given an array of integers `nums`. You need to sort the array in **non-decreasing order** using the **Selection Sort** algorithm.

### Definition:
A sorted array in **non-decreasing** order is one in which each element is **greater than or equal to** the one before it.

Examples:
- `[1, 2, 3, 4]` is non-decreasing ✅
- `[3, 2, 1]` is not non-decreasing ❌

---

## ✅ Approach:
We'll look at two approaches:
1. **Brute Force** – Using Python’s built-in sort method.
2. **Optimal** – Manual implementation using the Selection Sort algorithm.

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

## 2. Optimal Approach: Selection Sort

### 🔍 Intuition:
In each iteration, we find the **minimum element** from the unsorted part of the array and **swap** it with the first unsorted element.

### 🧾 Python Code:
```python
class Solution:
    def selectionSort(self, nums: list[int]) -> list[int]:
        n = len(nums)
        for i in range(n):
            min_index = i
            for j in range(i + 1, n):
                if nums[j] < nums[min_index]:
                    min_index = j
            nums[i], nums[min_index] = nums[min_index], nums[i]
        return nums
```

---

### 🧪 Sample Input:
```python
nums = [7, 4, 1, 5, 3]
```

### ✅ Sample Output:
```python
[1, 3, 4, 5, 7]
```

---

### 📊 Complexity Analysis:
- **Time Complexity:** O(n²)  
  Two nested loops: one for each element and another to find the min element.
- **Space Complexity:** O(1)  
  No extra data structures used.

---

## 📌 Summary:

| Approach      | Time Complexity  | Space Complexity | Notes                          |
|---------------|------------------|------------------|--------------------------------|
| Brute Force   | O(n log n)       | O(1)             | Uses efficient built-in sort   |
| Selection Sort| O(n²)            | O(1)             | Simple but inefficient for large arrays |

Selection Sort is useful for understanding sorting fundamentals but not suitable for large datasets.

---

