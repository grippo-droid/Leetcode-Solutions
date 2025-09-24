# 📈 Best Time to Buy and Sell Stock – C++ Solution

This file contains a solution for the **Best Time to Buy and Sell Stock** problem using C++.

---

## 📄 Problem Statement

You are given an array `prices` where `prices[i]` is the price of a given stock on the `iᵗʰ` day.  
You want to maximize your profit by choosing a **single day to buy** one stock and choosing a **different day in the future to sell** that stock.

Return the **maximum profit** you can achieve. If you cannot achieve any profit, return `0`.

---

## 💻 C++ Code Implementation

```cpp
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int result = 0;
        int i = 0, j = 1, count = 0;

        while (j != prices.size()) {
            if (prices[i] > prices[j]) {
                i = j + 1;
                swap(i, j);  // ensure we move the buying pointer forward
            } else {
                count = prices[j] - prices[i];
                if (count > result) {
                    result = count;
                }
                j++;
            }
        }
        return result;
    }
};
