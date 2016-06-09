# 137.Single Number II

**Problem:**
Given an array of integers, every element appears three times except for one. Find that single one.

Note:
Your algorithm should have a linear runtime complexity. Could you implement it without using extra memory?


**My Solutions:**

Date: June 9, 2016


    //22 ms
    class Solution {
    public:
        int singleNumber(vector<int>& nums) {
            int nl = nums.size();
            if(nl<4) return nums[0];
            sort(nums.begin(), nums.end());
            if(nums[0] != nums[1]) return nums[0];
            if(nums[nl-1] != nums[nl-2]) return nums[nl-1];
            for(int i=3; i<nl-3; i++){
                if(nums[i]!=nums[i-1] && nums[i]!=nums[i+1]) return nums[i];
            }
            // I dont know why this part is very important? 
            return nums[0];
        }
    };

