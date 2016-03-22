# 263.Ugly Number

**Problem:**

Write a program to check whether a given number is an ugly number.
Ugly numbers are positive numbers whose prime factors only include 2, 3, 5. For example, 6, 8 are ugly while 14 is not ugly since it includes another prime factor 7.
Note that 1 is typically treated as an ugly number.

**My Solutions:**

Date: March 18, 2016

    class Solution {
    public:
        bool isUgly(int num) {
            if(num <1) return false;
            else if(num == 1) return true;
            for(int i = 2; i <= 5; i++){
                while(num%i == 0){
                    num/=i;
                }
            }
            if(num != 1) return false;
            return true;
        }
    };