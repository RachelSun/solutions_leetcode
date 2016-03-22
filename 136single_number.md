# 136.Single Number
**Problem:**

Given an array of integers, every element appears twice except for one. Find that single one.

**Note:**
Your algorithm should have a linear runtime complexity. Could you implement it without using extra memory?

**My Solutions:**

Date: March 22, 2016

****

    // I don't want to use the sort() function. There must be some other way!
    
    class Solution {
    public:
        int singleNumber(vector<int>& nums) {
        sort(nums.begin(), nums.end());
        for(int i = 0; i<nums.size()-1; i+=2){
            if(nums[i]!=nums[i+1]){
                return nums[i];
            }
        }
        return nums[i];
        }
    };

****


    // Exceed the time limitation!
    
    class Solution {
    public:
        int singleNumber(vector<int>& nums) {
            vector<int>::iterator iter;
            if(nums.size() == 1) return nums[0];
            map<int, int> m;
            for(iter = nums.begin(); iter< nums.end(); iter++){
                m[nums[*iter]] +=1;
            }
            for(int i = 0; i< m.size(); i++){
                if(m[i] == 1)   return i;
            }
        }
    };


