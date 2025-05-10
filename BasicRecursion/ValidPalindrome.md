# 🧩 LeetCode 125: Valid Palindrome

## 🧠 Problem Statement

A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.
Given a string `s`, return `true` if it is a palindrome, or `false` otherwise.

### Examples:

**Example 1:**

Input: s = "A man, a plan, a canal: Panama"
Output: true
Explanation: "amanaplanacanalpanama" is a palindrome.

**Example 2:**

Input: s = "race a car"
Output: false
Explanation: "raceacar" is not a palindrome.

**Example 3:**

Input: s = " "
Output: true
Explanation: s is an empty string "" after removing non-alphanumeric characters.
Since an empty string reads the same forward and backward, it is a palindrome.

---

### Constraints:

- `1 <= s.length <= 2 * 10^5`
- `s` consists only of printable ASCII characters.

---

## ✅ Approach

### Solution 1: Two Pointers Approach (Optimal)

1. Initialize two pointers, `left` at the beginning (`0`) and `right` at the end (`len(s) - 1`) of the string.
2. While `left` is less than `right`:
   - Skip non-alphanumeric characters by moving the pointers inward.
   - Compare the characters at `left` and `right` in a case-insensitive manner.
   - If they are not equal, return `false`.
3. If the loop completes without returning `false`, return `true`.

```python
class Solution:
    def isPalindrome(self, s: str) -> bool:
        left, right = 0, len(s) - 1

        while left < right:
            if not s[left].isalnum():
                left += 1
            elif not s[right].isalnum():
                right -= 1
            elif s[left].lower() != s[right].lower():
                return False
            else:
                left += 1
                right -= 1

        return True

```
---

### Solution 2: String Cleaning Approach

1. Convert the string to lowercase.

2. Remove all non-alphanumeric characters.

3. Check if the cleaned string is equal to its reverse.

```python
class Solution:
    def isPalindrome(self, s: str) -> bool:
        cleaned_str = ''.join(c.lower() for c in s if c.isalnum())
        return cleaned_str == cleaned_str[::-1]

```
---

### Complexity Analysis:
**Time Complexity:** O(N)
O(n), where n is the length of the string s. Both solutions traverse the string at most once.
**Space Complexity:** 
Solution 1: O(1), as it uses only two pointers.
Solution 2: O(n), due to the additional space used for the cleaned string.

---

Reversing an array in-place is a fundamental operation in computer science. Using recursion or iteration, we can achieve this efficiently. The recursive approach provides a clear and elegant solution, while the iterative approach offers better space efficiency.

---
