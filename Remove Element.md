# 🗑️ Remove Element – C++ Solution

This file contains a solution for the **Remove Element** problem using C++.

---

## 📄 Problem Statement

Given an integer array `nums` and an integer `val`, remove all occurrences of `val` **in-place**.  
The order of the elements may be changed.  
Then return the number of elements in `nums` which are not equal to `val`.

---

## 💻 C++ Code Implementation

```cpp
class Solution {
public:
    int removeElement(vector<int>& nums, int val) {
        int start = 0;
        int count = 0;
        int end = nums.size() - 1;

        while (start <= end) {
            if (nums[end] == val) {
                end--;
                count++;
            } else if (nums[start] == val) {
                swap(nums[start], nums[end]);
                end--;
                count++;
            } else {
                start++;
            }
        }
        return nums.size() - count;
    }
};
