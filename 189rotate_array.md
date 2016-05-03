# 189.Rotate Array

** Problem:**

Rotate an array of n elements to the right by k steps.

    For example, with n = 7 and k = 3, the array [1,2,3,4,5,6,7] is rotated to [5,6,7,1,2,3,4].

Note:
Try to come up as many solutions as you can, there are at least 3 different ways to solve this problem.


**My Solutions:**

Date: May 3, 2016

    // Solution 1, 56ms
    // Use the erase function in the loop everytime when move a number.----> slow

    class Solution {
    public:
        void rotate(vector<int>& nums, int k) {
            int nl = nums.size();
            k = k%nl;
            int m = nl-k;
            while(m){
                nums.push_back(nums[0]);
                nums.erase(nums.begin());
                m--;
            }
        }
    };
    
    
    // Solution 2, 24ms
    // Move the part of erasing the elements outside of the loop to reduce operation time.
    
    class Solution {
    public:
        void rotate(vector<int>& nums, int k) {
            int nl = nums.size();
            k = k%nl;
            for(int i = 0; i< nl-k; i++){
                nums.push_back(nums[i]);
            }
            nums.erase(nums.begin(), nums.begin()+m);
        }
    };
    

