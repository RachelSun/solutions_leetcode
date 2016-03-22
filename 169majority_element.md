# 169.Majority Element
**Problem:**

Given an array of size n, find the majority element. The majority element is the element that appears more than ⌊ n/2 ⌋ times.
You may assume that the array is non-empty and the majority element always exist in the array.

**My Solutions:**

Date: March 16, 2016

    class Solution {
    public:
        int majorityElement(vector<int>& nums) {
            if(nums.size() == 1)
            return nums[0];
            map<int,int > v;
            for(int i=0; i<nums.size(); i++){
                v[nums[i]] = v[nums[i]]+1;
                if(v[nums[i]]>nums.size()/2){
                    return nums[i];
                }
            }
        }
    };


