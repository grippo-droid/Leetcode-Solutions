# 🗂️ Remove Duplicates from Sorted Array – C++ Solution

This file contains a solution for the **Remove Duplicates from Sorted Array** problem using C++.

---

## 📄 Problem Statement

Given an integer array `nums` sorted in **non-decreasing order**, remove the duplicates **in-place** such that each unique element appears only once.  
Return the number of unique elements in `nums`.  

The relative order of the elements should be kept the same.

---

## 💻 C++ Code Implementation

```cpp
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        int i = 0, j = 0, count = 0;

        while (j + 1 != nums.size()) {
            if (nums[j] == nums[j + 1]) {
                j = j + 1;  // skip duplicate
            } else {
                nums[i + 1] = nums[j + 1];  // place next unique element
                count = count + 1;
                i = i + 1;
                j = j + 1;
            }
        }
        return count + 1;  // +1 because first element is always unique
    }
};
