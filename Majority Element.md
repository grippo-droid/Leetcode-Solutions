# 🏆 Majority Element – C++ Solution

This file contains a solution for the **Majority Element** problem using C++.

---

## 📄 Problem Statement

Given an array `nums` of size `n`, return the **majority element**.  
The majority element is the element that appears **more than ⌊n / 2⌋ times**.

You may assume that the majority element always exists in the array.

---

## 💻 C++ Code Implementation

```cpp
class Solution {
public:
    int majorityElement(vector<int>& nums) {
        int i = 0, count = 1;
        sort(nums.begin(), nums.end());

        while (i < nums.size() - 1) {
            if (nums[i] == nums[i + 1]) {
                count = count + 1;
                i = i + 1;
            } else {
                if (count > (nums.size() / 2)) {
                    return nums[i];
                } else {
                    count = 1;
                    i = i + 1;
                }
            }
        }

        if (count > (nums.size() / 2)) {
            return nums[i];
        }
        return 0;  // theoretically should never hit this case if majority element exists
    }
};
