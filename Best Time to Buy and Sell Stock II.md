# 📈 Best Time to Buy and Sell Stock II – C++ Solution

This file contains a solution for the **Best Time to Buy and Sell Stock II** problem using C++.

---

## 📄 Problem Statement

You are given an array `prices` where `prices[i]` is the price of a given stock on the `iᵗʰ` day.  

On each day, you may decide to **buy** and/or **sell** the stock.  
You can only hold at most one share of the stock at a time, but you can buy it again after selling.

Return the **maximum profit** you can achieve.

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
                swap(i, j);  // move buy pointer forward
            } else {
                count = prices[j] - prices[i];
                result = result + count;  // accumulate profit
                i++;
                j++;
            }
        }
        return result;
    }
};
