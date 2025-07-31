# 📌 Merge Sort

## 🧠 Problem Statement:
Given an array of `N` integers, write a program to sort the array using the **Merge Sort** algorithm.

---

### 🧾 Examples:

**Example 1:**
```
Input:  N = 5, array = [4, 2, 1, 6, 7]
Output: [1, 2, 4, 6, 7]
```

**Example 2:**
```
Input:  N = 5, array = [3, 2, 8, 5, 1, 4, 23]
Output: [1, 2, 3, 4, 5, 8, 23]
```

---

## ✅ Approach:

We will explore two approaches:

1. **Brute Force** – Using Python’s built-in `sort()` method.
2. **Optimal** – Manual implementation using **Merge Sort**.

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

## 2. Optimal Approach: Merge Sort

### 🔍 Intuition:
### ✅ Steps:

1. Divide the array using indices: `low` to `mid`, and `mid+1` to `high`.
2. Recursively call `mergeSort()` on both halves.
3. Merge the two sorted halves using the `merge()` function.

**Base Case:**  
When `low >= high`, the recursion stops.

### 💻 Python Code:
```python
def merge(arr, low, mid, high):
    temp = []
    left = low
    right = mid + 1

    # Merge the two sorted halves
    while left <= mid and right <= high:
        if arr[left] <= arr[right]:
            temp.append(arr[left])
            left += 1
        else:
            temp.append(arr[right])
            right += 1

    # Copy remaining elements of left half
    while left <= mid:
        temp.append(arr[left])
        left += 1

    # Copy remaining elements of right half
    while right <= high:
        temp.append(arr[right])
        right += 1

    # Copy temp[] back to arr[]
    for i in range(len(temp)):
        arr[low + i] = temp[i]

def mergeSort(arr, low, high):
    if low >= high:
        return
    mid = (low + high) // 2
    mergeSort(arr, low, mid)
    mergeSort(arr, mid + 1, high)
    merge(arr, low, mid, high)

# Example usage:
arr = [3, 2, 8, 5, 1, 4, 23]
mergeSort(arr, 0, len(arr) - 1)
print("Sorted array:", arr)

```

---

### 📊 Complexity:
- Time: 
  - Best, Average, Worst: O(N log N)
- Space: O(N) (due to temporary array)

---

## 🔚 Summary Table:

| Approach       | Time Complexity | Space Complexity | Notes                                  |
|----------------|------------------|-------------------|----------------------------------------|
| Brute Force    | O(n log n)       | O(1)              | Uses built-in sort                     |
| Insertion Sort | O(n²)            | O(1)              | Efficient for small or nearly sorted arrays |

---

