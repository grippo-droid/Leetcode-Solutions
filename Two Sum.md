# 🧮 Two Sum – C++ Solution

This file contains a simple **brute-force solution** for the classic **Two Sum** problem using C++.

---

## 📄 Problem Statement

Given an array of integers `nums` and an integer `target`, return *indices of the two numbers such that they add up to `target`*.

You may assume that each input would have **exactly one solution**, and you may not use the same element twice.

---

## 💻 C++ Code Implementation

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        vector<int> v1;
        bool found = false;

        for (int i = 0; i < nums.size(); i++) {
            for (int j = 0; j < nums.size(); j++) {
                if (i == j) {
                    continue;  // skip if both indices are the same
                }
                if (nums[i] + nums[j] == target) {
                    v1.push_back(i);
                    v1.push_back(j);
                    found = true;
                    break;  // exit inner loop
                }
            }
            if (found) {
                break;  // exit outer loop
            }
        }
        return v1;
    }
};

