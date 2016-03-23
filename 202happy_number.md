# 202.Happy Number

**Problem:**

Write an algorithm to determine if a number is "happy".

A happy number is a number defined by the following process: Starting with any positive integer, replace the number by the sum of the squares of its digits, and repeat the process until the number equals 1 (where it will stay), or it loops endlessly in a cycle which does not include 1. Those numbers for which this process ends in 1 are happy numbers.

Example: 19 is a happy number

    1^2 + 9^2 = 82
    8^2 + 2^2 = 68
    6^2 + 8^2 = 100
    1^2 + 0^2 + 0^2 = 1
    
    
**My Solutions:**

Date: March 22, 2016

    //Acknowledgement: A special gratitude I would like to tribute to Mr. Lu.
    
    class Solution {
    public:
    
    map<int, int > m;
    bool isHappy(int n){
            int sum = 0;
            if(n == 1) return true;
            while(n){
                sum += (n%10)*(n%10);
                n/=10;
            }
            m[sum]++;
            if(sum == 1) return true;
            if(m[sum] == 2 ) return false;
            isHappy(sum);
        }   
    };
    
   
    **Note: **

    As mentioned in the description, if the input number is not a happy number, the code loops endlessly in a cycle which does not include 1. 

    For example: 

    If the input number is 2, the following numbers will repeat:

    [4
    16
    37
    58
    89
    145
    42
    20]