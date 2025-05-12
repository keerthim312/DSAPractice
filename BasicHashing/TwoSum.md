# 🧩 LeetCode 1: Two Sum

## 🧠 Problem Statement

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to the target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

**Example 1:**

Input: nums = [2,7,11,15], target = 9  
Output: [0,1]
Explanation: nums[0] + nums[1] == 9, so we return [0, 1]

**Example 2:**

Input: nums = [3,2,4], target = 6  
Output: [1,2]

**Example 3:**

Input: nums = [3,3], target = 6  
Output: [0,1]

---

### Constraints:

2 <= nums.length <= 10⁴

-10⁹ <= nums[i] <= 10⁹

-10⁹ <= target <= 10⁹

Only one valid answer exists.

---

## ✅ Approach

### Hash Map (Optimal)

This problem can be efficiently solved using a hash map to store previously seen numbers and their indices. This avoids the brute force O(n²) time complexity.

🔍 Key Idea:
While iterating over the array, for each element nums[i], compute diff = target - nums[i].

Check if diff exists in the hash map.

If it does, return [map[diff], i].

Otherwise, store nums[i] in the map with its index.

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        num_map = {}  # stores number -> index
        for i, num in enumerate(nums):
            diff = target - num
            if diff in num_map:
                return [num_map[diff], i]
            num_map[num] = i

```
---

### Complexity Analysis:
**Time Complexity:** O(N)

We traverse the list only once.

**Space Complexity:** 

In the worst case, we store all n elements in the hash map.

---

This solution is both efficient and easy to implement.
The hash map allows us to find complements in constant time.

---
