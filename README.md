# 167. Two Sum II - Input Array Is Sorted

## 🧩 Problem Statement
Given a **1-indexed** array of integers `numbers` that is sorted in **non-decreasing order**, find two numbers such that they add up to a specific `target`.

Return the indices of the two numbers (1-based indexing).

- Exactly one solution exists.
- You may not use the same element twice.
- Use only constant extra space.

---

## 💡 Approach: Two Pointer Technique

Since the array is sorted, we can use two pointers:

- Start one pointer at the beginning (`left`)
- Start another pointer at the end (`right`)

### Steps:
1. Calculate `sum = numbers[left] + numbers[right]`
2. If `sum == target` → return indices
3. If `sum < target` → move `left++`
4. If `sum > target` → move `right--`

---

## 🚀 Code (C++)

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& numbers, int target) {
        int left = 0;
        int right = numbers.size() - 1;

        while (left < right) {
            int sum = numbers[left] + numbers[right];

            if (sum == target) {
                return {left + 1, right + 1};
            } 
            else if (sum < target) {
                left++;
            } 
            else {
                right--;
            }
        }

        return {};
    }
};
