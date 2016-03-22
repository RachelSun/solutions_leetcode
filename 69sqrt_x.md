# 69.Sqrt (x)

**Problem:**

Implement int sqrt(int x).

Compute and return the square root of x.

**My Solutions:**

Date: March 21, 2016

    // I think this code used the pow() function. It should be avoided?
    
    class Solution {
    public:
        int mySqrt(int x) {
        return pow(10, log10(x)/2.0);
        }
    };
    
Note:

If I use exp(log(x)/2.0), I can not get the right answer.
