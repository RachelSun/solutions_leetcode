# 171.Excel Sheet Column Number

** Problem:**

Related to question Excel Sheet Column Title

Given a column title as appear in an Excel sheet, return its corresponding column number.

For example:

    A -> 1
    B -> 2
    C -> 3
    ...
    Z -> 26
    AA -> 27
    AB -> 28 
    
    
   **My Solutions:**
  
  Date: April 4, 2016
  
      // **8ms**
      class Solution {
      public:
         int titleToNumber(string s) {
         int sum = 0, sl = s.length();
         for(int i = 0; i < s.length(); i++)
         {
             sum += (s[i] - 'A' + 1)* pow(26, sl - 1 - i);
         }
         return sum;
         }
      };

  
    // **28ms**
    class Solution {
    public:
        int titleToNumber(string s) {
            int sl = s.length();
        // If the string is empty then return -1
            if(sl == 0) return -1;
            
        //Create a hash table to store all the char and corresponding number.
            map<char, int> m;
            int cnt = 1, sum = 0, flag = 1;
            for(char i = 'A'; i<='Z'; i++ ){
                m[i] = ++cnt;
            }
        // Processe the string one char by one char
            for(int i = sl; i>0; i--){
                if(flag){
                    sum = sum+ m[s[i-1]];
                    flag = 0;
                }
                else{
                    sum += m[s[i-1]]*pow(26,sl-i);
                }
            }
            return sum;
        }
    };
