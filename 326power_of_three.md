# 326.Power of Three


**Problem:**

Given an integer, write a function to determine if it is a power of three.
Follow up:
Could you do it without using any loop / recursion?

**My Solutions:**

Date: March 21. 2016

    class Solution {
    public:
        bool isPowerOfThree(int n) {
            if(n == 1) return true;
            return log10(n)/log10(3) == int(log10(n)/log10(3));
        }
    };

