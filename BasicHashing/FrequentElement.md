# 🧩 LeetCode 1838: Frequency of the Most Frequent Element

## 🧠 Problem Statement

Given an integer array `nums` and an integer `k`, you can perform at most `k` operations on the array. In each operation, you can choose an index of `nums` and increment the element at that index by `1`. Your task is to return the maximum possible frequency of any element after performing at most `k` operations.

### Examples

**Example 1:**

Input: `nums = [1,2,4], k = 5`

Output: `3`

Explanation: Increment the first element three times and the second element two times to make `nums = [4,4,4]`. The frequency of `4` is `3`.

**Example 2:**

Input: `nums = [1,4,8,13], k = 5`

Output: `2`

Explanation: There are multiple optimal solutions:

- Increment the first element three times to make `nums = [4,4,8,13]`. The frequency of `4` is `2`.
- Increment the second element four times to make `nums = [1,8,8,13]`. The frequency of `8` is `2`.
- Increment the third element five times to make `nums = [1,4,13,13]`. The frequency of `13` is `2`.

**Example 3:**

Input: `nums = [3,9,6], k = 2`

Output: `1`

### Constraints

- `1 <= nums.length <= 10⁵`
- `1 <= nums[i] <= 10⁵`
- `1 <= k <= 10⁵`

## ✅ Approach

### Sliding Window (Optimal)

This problem can be efficiently solved using the sliding window technique. The idea is to sort the array and then use a sliding window to find the maximum frequency of any element after performing at most `k` operations.

#### Steps:

1. **Sort the Array:** Sorting helps in grouping elements that are close in value, minimizing the number of operations required to make them equal.

2. **Sliding Window:** Use two pointers (`left` and `right`) to maintain a window of elements. The window represents a subarray where all elements can be made equal with at most `k` operations.

3. **Calculate Operations:** For each window, calculate the total number of operations required to make all elements equal to the rightmost element of the window. If the required operations exceed `k`, move the left pointer to reduce the window size.

4. **Update Maximum Frequency:** Keep track of the maximum frequency of any element that can be achieved within the operation limit.

```python
class Solution:
    def maxFrequency(self, nums: List[int], k: int) -> int:
        nums.sort()
        left = 0
        total = 0
        max_freq = 0

        for right in range(len(nums)):
            total += nums[right]

            # Check if the current window is valid
            while (right - left + 1) * nums[right] - total > k:
                total -= nums[left]
                left += 1

            max_freq = max(max_freq, right - left + 1)

        return max_freq

```
---

### Complexity Analysis:
**Time Complexity:** O(n log n)

Sorting the array takes O(n log n), where n is the length of the array.

The sliding window operation takes O(n).

Therefore, the total time complexity is O(n log n).

**Space Complexity:** O(1)

The space complexity is O(1) since we are using only a few extra variables.

---

Frequency of the Most Frequent Element" effectively demonstrates how sorting and the sliding window technique can be combined to solve optimization problems efficiently. By sorting the array and using two pointers to maintain a window of elements, we can determine the maximum possible frequency of any element after performing at most `k` increment operations.


---
