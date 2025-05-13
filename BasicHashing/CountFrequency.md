# 🧮 Count Frequency of Each Element in an Array

## 🧠 Problem Statement

Given an array, determine the number of occurrences of each element in the array.

#### Example :
Input:
arr = [10, 5, 10, 15, 10, 5]

Output:
```
10 3
5 2
15 1

```
Explanation:

10 occurs 3 times in the array.

5 occurs 2 times in the array.

15 occurs 1 time in the array.

---

## ✅ Approach

### Using Hash Map

🔍 Key Idea
We can efficiently count the frequency of each element in an array by utilizing a hash map (or dictionary in Python). This allows us to store each element as a key and its frequency as the corresponding value.

We start by creating an empty dictionary mp to store the frequency of each element.

We loop through each element in the array.

If the element is already a key in the dictionary, increment its value by 1.

If the element is not present in the dictionary, add it with a value of 1.

After populating the dictionary with frequencies, we iterate through the dictionary and print each key-value pair.

```python
def Frequency(arr, n):
    mp = {}
    for i in range(n):
        if arr[i] in mp:
            mp[arr[i]] += 1
        else:
            mp[arr[i]] = 1
    for x in mp:
        print(x, mp[x])

if __name__ == '__main__':
    arr = [10, 5, 10, 15, 10, 5]
    n = len(arr)
    Frequency(arr, n)

```
---

### Complexity Analysis:
**Time Complexity:** O(N)

where n is the number of elements in the array. The function iterates through the list once, and dictionary operations (in and assignment) are O(1) on average.

**Space Complexity:** O(K)

where k is the number of unique elements in the array. In the worst case, when all elements are unique, the dictionary will store n entries.

---

Counting the frequency of each element in an array is a fundamental task in data processing. Utilizing a hash map (or dictionary in Python) offers an efficient and straightforward approach to achieve this.

---
