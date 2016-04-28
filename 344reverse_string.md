# 344.Reverse String

** Problems:**
Write a function that takes a string as input and returns the string reversed.

    Example:
    Given s = "hello", return "olleh".
    
    
** My Solution:**

Date: April 28, 2016

    class Solution {
    public:
        string reverseString(string s) {
            int sl = s.length();
            if(sl== 0 ||sl == 1) return s;
            for(int i = 0; i<sl/2;i++){
               char temp = s[i];
               s[i] = s[sl-i-1];
               s[sl-i-1] = temp;
            }
            return s;
        }
    };