# 50.Pow(x, n)

**Problem:**

Implement pow(x, n).

**My Solutions:**

    
   Date: March 22,2016
   
    // This one pass the test. :)
    class Solution {
    public:
        double myPow(double x, int n) {
            if(x<0 && n%2 != 0)
                return -exp(n*log(-x));
            if(x<0 && n%2 == 0)
                return exp(n*log(-x));
            return exp(n*log(x));
        }
    };

Date: March, 21, 2016

    // This one is not accepted since it takes very long time to execute.
    class Solution {
    public:
        double myPow(double x, int n) {
            double mul = 1.0;
            while(n){
                mul = mul*x;
                n--;
            }
            return mul;
        }
    };
    