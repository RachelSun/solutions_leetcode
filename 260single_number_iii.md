# 260.Single Number III

**Problem:**
Given an array of numbers nums, in which exactly two elements appear only once and all the other elements appear exactly twice. Find the two elements that appear only once.

      For example:

      Given nums = [1, 2, 1, 3, 2, 5], return [3, 5].

Note:
The order of the result is not important. So in the above example, [5, 3] is also correct.
Your algorithm should run in linear runtime complexity. Could you implement it using only constant space complexity?


**My Solutions:**

Date: June 9, 2016

      // I guess this problem can be solved by bit manipulation
      // 24ms
      // Sort and Compare
      class Solution {
      public:
          vector<int> singleNumber(vector<int>& nums) {
              // length of the vector 
              int nl = nums.size();
              if(nl<4) return nums;
              
              // Create a vector to save the result
              // The initialization of a vector
              vector<int> result (2,0);

              // Sort and Compare
              sort (nums.begin(), nums.end()); 
              int cnt = 0;
              // if the first number is the target number
              if(nums[0]!= nums[1]) {
                 result[cnt] = nums[0];
                 cnt++;
              }
              for(int i=1; i<nl-1; i++){
                  if(nums[i] != nums[i+1] && nums[i-1]!=nums[i]){
                      result[cnt] = nums[i];
                      cnt++;
                  } 
              }
              // if the last number is the target number.
              if(nums[nl-1]!=nums[nl-2]){
                  result[cnt] = nums[nl-1];
              }
              return result;
          }
      };


