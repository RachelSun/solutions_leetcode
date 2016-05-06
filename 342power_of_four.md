# 342.Power of Four
**Problem:**

Given an integer (signed 32 bits), write a function to check whether it is a power of 4.

    Example:
    Given num = 16, return true. Given num = 5, return false.

Follow up: Could you solve it without loops/recursion?

**Solutions:**

Data: May 06,2016

    // 8ms
    class Solution {
    public:
        bool isPowerOfFour(int num) {
            if(log(num)/log(4) == int(log(num)/log(4))) return true;
            else return false;
        }
    };