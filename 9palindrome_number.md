# 9.Palindrome Number

**Problem:**

Determine whether an integer is a palindrome. Do this without extra space.

**My Solutions:**

Date: March 22, 2016

    class Solution {
    public:
        bool isPalindrome(int x) {
            if(x == 0) return true;
            int rev = 0;
            int temp;
            if(x<0) temp = x*(-1);
            else temp = x;
            while(x){
                rev = (rev*10) + (x%10);
                x = x/10;
            }
            if(rev == temp )  return true;
            return false;
        }
    };