# 70.Climbing Stairs

**Problem:**

You are climbing a stair case. It takes n steps to reach to the top.

Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top? 

**My Solutions:**

Date: March 23, 2016

    class Solution {
    public:
        int climbStairs(int n) {
            int first = 0, second= 1;
            int sum = 1;
            for(int i = 1; i<=n; i++){
                sum = first+second;
                first = second;
                second = sum;
            }
            return sum;
        }
    };