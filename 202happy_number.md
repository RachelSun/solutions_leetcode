# 202.Happy Number

**Problem:**

Write an algorithm to determine if a number is "happy".

A happy number is a number defined by the following process: Starting with any positive integer, replace the number by the sum of the squares of its digits, and repeat the process until the number equals 1 (where it will stay), or it loops endlessly in a cycle which does not include 1. Those numbers for which this process ends in 1 are happy numbers.

Example: 19 is a happy number

  1<sup>2</sup> + 9<sup>2</sup> = 82
  
   8<sup>2</sup> + 2<sup>2</sup> = 68
    
   6<sup>2</sup> + 8<sup>2</sup> = 100
    
   1<sup>2</sup> + 0<sup>2</sup> + 0<sup>2</sup> = 1
    
    
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

    As mentioned in the problem description, if the input number is not a happy number, the code loops endlessly in a cycle which does not include 1. 

    For example: 

    If the input number is 2, the following sequence will repeat:

    [4, 16, 37, 58, 89, 145, 42, 20]
    
    By using the hash map: map<int, int > m; we can track whether the numbers in the sequence occurs  multiple times or not. If the m[sum] occurs twice (at least), which means that the input number is not a happy number, then return false.
    
    If the sum equals to 1, which means that the input number is a happy number, then return true.