# 119.Pascal's Triangle II

**Problem:**
Given an index k, return the kth row of the Pascal's triangle.

    For example, given k = 3,
    Return [1,3,3,1].

Note:
Could you optimize your algorithm to use only O(k) extra space?

** My Solutions:**

Date: May 3, 2016

    // 2ms
    class Solution {
    public:
        vector<int> getRow(int rowIndex) {
            int rowNum = rowIndex+1;
            vector<int> vec(rowNum,0);
            vec[0] = 1;
            while(rowNum--){
                for(int i = 1; i<= rowNum; i++){
                    vec[i] +=vec[i-1];
                }
            }
            return vec;
        }
    };