# 121.Best Time to Buy and Sell Stock

**Problem:**
Say you have an array for which the ith element is the price of a given stock on day i.

If you were only permitted to complete at most one transaction (ie, buy one and sell one share of the stock), design an algorithm to find the maximum profit.

**Solutions:**

Date: May 6, 2016

    // 12 ms
    class Solution {
    public:
        int maxProfit(vector<int>& prices) {
            int pSize = prices.size();
            int buy = INT_MAX;
            int maxProfit = 0;
            for(int i = 0; i< pSize; i++){
                buy = min(buy, prices[i]);
                maxProfit = max(prices[i]-buy, maxProfit);
            }
            return maxProfit;
        }
    };
