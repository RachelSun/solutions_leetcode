# 27.Remove Elements

**Problem:**

Given an array and a value, remove all instances of that value in place and return the new length.

Do not allocate extra space for another array, you must do this in place with constant memory.

The order of elements can be changed. It doesn't matter what you leave beyond the new length.

**Example:**

Given input array nums = [3,2,2,3], val = 3

Your function should return length = 2, with the first two elements of nums being 2.


**My Solutions:**

Date: March 21, 2016

    class Solution {
    public:
        int removeElement(vector<int>& nums, int val) {
            vector<int>::iterator iter;
            for(iter = nums.begin(); iter<nums.end(); iter++){
                if(*iter == val){
                    iter = nums.erase(iter);
                    iter--;
                }
            }
            return nums.size();
        }
    };

