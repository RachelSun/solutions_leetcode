# 7.Reverse Integer

**Problem:**

Reverse digits of an integer.

    Example1: x = 123, return 321

    Example2: x = -123, return -321 
    
Note: Overflow problem

** My Solutions:**

Date: April 06, 2016


    // 8ms
    class Solution {
    public:
        int reverse(int x) {
        // The interger range is [-2,147,483,648 2,147,483,647]
        // Use the long int 
            long int sum = 0;
            while(x/10 ){
                sum = sum*10+x%10;
                x/=10;
            }
            sum = sum*10+x;
            if(sum>INT_MAX || sum<INT_MIN) return 0;
            return sum;
        }
    };
