# 📌 Insertion Sort

## 🧠 Problem Statement:
Given an array of `N` integers, write a program to sort the array using the **Insertion Sort** algorithm.

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
2. **Optimal** – Manual implementation using **Insertion Sort**.

---

## 1. Brute Force Using Built-in Sort

### 🔍 Intuition:
Use Python’s built-in sorting method which uses Timsort (Hybrid of Merge + Insertion sort).

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
- Iterate from index `1` to `n - 1`.
- Pick the element and shift larger elements of the sorted segment to the right.
- Insert the element in its correct position.

### 🔄 Dry Run:

- Index `i=0`: Already sorted (single element)
- `i=1`: 46 > 13 → No change
- `i=2`: 24 < 46 → swap with 46 → now array: [13, 24, 46,...]
- `i=4`: 20 < 52 → keep shifting 52, 46... insert at correct position
- Continue till fully sorted

### 💻 Python Code:
```python
class Solution:
    def insertionSort(self, nums: list[int]) -> list[int]:
        for i in range(1, len(nums)):
            key = nums[i]
            j = i - 1
            while j >= 0 and nums[j] > key:
                nums[j + 1] = nums[j]
                j -= 1
            nums[j + 1] = key
        return nums
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
  - Best Case: O(n)
  - Worst Case: O(n²)
- Space: O(1) (In-place)

---

## 🔚 Summary Table:

| Approach       | Time Complexity | Space Complexity | Notes                                  |
|----------------|------------------|-------------------|----------------------------------------|
| Brute Force    | O(n log n)       | O(1)              | Uses built-in sort                     |
| Insertion Sort | O(n²)            | O(1)              | Efficient for small or nearly sorted arrays |

---

