# 📌 Quick Sort

## 🧠 Problem Statement:
Given an array of `N` integers, write a program to sort the array using the **Quick Sort** algorithm.

---

### 🧾 Examples:

**Example 1:**
```
Input:  N = 6, array = [13, 46, 24, 52, 20, 9]
Output: [9, 13, 20, 24, 46, 52]
```

**Example 2:**
```
Input:  N = 5, array = [5, 4, 3, 2, 1]
Output: [1, 2, 3, 4, 5]
```

---

## ✅ Approach:

We will explore two approaches:

1. **Brute Force** – Using Python’s built-in `sort()` method.
2. **Optimal** – Manual implementation using **Quick Sort**.

---

## 1. Brute Force Using Built-in Sort

### 🔍 Intuition:
Use Python’s built-in sorting method which uses Timsort.

### 💻 Python Code:
```python
class Solution:
    def sortArray(self, nums: list[int]) -> list[int]:
        nums.sort()
        return nums
```

### 📊 Complexity:
- Time: O(n log n)
- Space: O(1)

---

## 2. Optimal Approach: Insertion Sort

### 🔍 Intuition:
Choose a pivot element.

Partition the array so that elements less than pivot are on the left, and greater on the right.

Recursively apply this strategy on both halves.

### 🔄 Dry Run:

Array: [13, 46, 24, 52, 20, 9]
Pivot = 9
→ Partitioned: [9] | [46, 24, 52, 20, 13]
Recursively apply on right part:
→ Pivot = 13
→ Partitioned: [13] | [46, 24, 52, 20]
... and so on.

### 💻 Python Code:
```python
class Solution:
    def quickSort(self, nums: list[int], low: int, high: int) -> None:
        if low < high:
            pi = self.partition(nums, low, high)
            self.quickSort(nums, low, pi - 1)
            self.quickSort(nums, pi + 1, high)

    def partition(self, nums: list[int], low: int, high: int) -> int:
        pivot = nums[high]
        i = low - 1
        for j in range(low, high):
            if nums[j] <= pivot:
                i += 1
                nums[i], nums[j] = nums[j], nums[i]
        nums[i + 1], nums[high] = nums[high], nums[i + 1]
        return i + 1

```

---

### 🧪 Sample Input:
```python
nums = [13, 46, 24, 52, 20, 9]
```

### ✅ Output:
```python
[9, 13, 20, 24, 46, 52]
```

---

### 📊 Complexity:
- Time: 
  - Best & Average Case: O(n log n)
  - Worst Case: O(n²)
- Space: O(log n) for recursion stack (in-place)

---

## 🔚 Summary Table:

| Approach    | Time Complexity             | Space Complexity | Notes                                       |
| ----------- | --------------------------- | ---------------- | ------------------------------------------- |
| Brute Force | O(n log n)                  | O(1)             | Uses built-in sort                          |
| Quick Sort  | O(n log n) avg, O(n²) worst | O(log n)         | Fastest on average, but worst-case possible |

---

