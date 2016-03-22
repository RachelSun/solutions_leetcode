# 283.Move Zeroes

**Problem:**

Given an array nums, write a function to move all 0's to the end of it while maintaining the relative order of the non-zero elements.

For example, given nums = [0, 1, 0, 3, 12], after calling your function, nums should be [1, 3, 12, 0, 0].

**Note:**
You must do this in-place without making a copy of the array.
Minimize the total number of operations

**My Solutions:**

Date: March 16, 2016

    class Solution{
    public:
        void moveZeroes(vector<int>& nums){
            int cnt = 0;
            vector<int>::iterator iter;
            if(!nums.empty()){
                for(iter = nums.begin(); iter<nums.end(); iter++){
                    if(*iter == 0){
                        nums.erase(iter);
                        iter = iter-1;
                        cnt++;
                    }
                }
                for(int j=0; j<cnt; j++){
                    nums.push_back(0);
                }
            }
        }
    }; 


136.Single Number



