# 🧩 Problem Statement

Given an array `arr` of `n` elements, the task is to **reverse the given array** in-place.

The reversal of the array should modify the original array itself, without using any additional space for another array.

---

## 🧠 Understanding the Problem

The task is to reverse the array without using extra space. The reversal should be done in-place by swapping elements from the beginning and the end of the array.

Formally:
- Reverse the array `[1, 2, 3, 4, 5]` → `[5, 4, 3, 2, 1]`.
- The idea is to swap the first and last elements, then move inward and swap again.

---

## ✅ Approach:

To reverse the array, we use two pointers:
1. One pointer starts at the beginning (`left`).
2. The second pointer starts at the end (`right`).

We then:
- Swap the elements at the two pointers.
- Move the `left` pointer forward and the `right` pointer backward until they meet.

This process works in-place, meaning no additional array is used.

---

## 🧑‍💻 Python Code:

```python
class Solution:
    def reverse(self, arr, n):
        def helper(left, right):
            if left >= right:
                return
            arr[left], arr[right] = arr[right], arr[left]  # Swap the elements
            helper(left + 1, right - 1)  # Recurse with updated pointers
        
        helper(0, n - 1)  # Start recursion with full range of the array

# Example usage:
arr = [1, 2, 3, 4, 5]
n = len(arr)
sol = Solution()
sol.reverse(arr, n)
print(arr)  # Output: [5, 4, 3, 2, 1]

```
---

#### Sample Input:
n = 5
arr = [1, 2, 3, 4, 5]

#### Sample Output:
[5, 4, 3, 2, 1]

---

### Complexity Analysis:
**Time Complexity:** O(N)
The function makes a recursive call for each pair of elements in the array, so the time complexity is linear with respect to the number of elements in the array.

**Space Complexity:** O(N)
The space complexity is O(N) due to the recursive call stack used by the helper function. Each recursive call adds a new frame to the stack until the base case is reached.

---

### Recursive Tree:
```
reverse([1, 2, 3, 4, 5])
    ↳ swap(0, 4) → [5, 2, 3, 4, 1]
    ↳ reverse([2, 3, 4])  -> swap(1, 3) → [5, 4, 3, 2, 1]
    ↳ reverse([3])  -> Base case (left == right)
Final reversed array = [5, 4, 3, 2, 1]

```
---

This is an efficient solution to reverse an array in-place using recursion. By using the two-pointer technique and recursion, we can directly modify the original array, keeping the space complexity to a minimum.

---
