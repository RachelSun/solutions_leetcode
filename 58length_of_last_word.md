# 58.Length of Last Word

**Problem:**

Given a string s consists of upper/lower-case alphabets and empty space characters ' ', return the length of last word in the string.

If the last word does not exist, return 0

Note: A word is defined as a character sequence consists of non-space characters only.

For example, Given s = "Hello World", return 5.

**My Solutions:**

Date: March 22, 2016

    class Solution {
    public:
        int lengthOfLastWord(string s) {
            // Empty string
            if(s.length() == 0) return 0;
            // Count the number of chars
            int cnt = 0;
            // Skip the last '/0', the end flag of the string
            for(int i = s.length()-1; i>=0; i--) {
                if(int(s[i]) == 32 && cnt!=0) break;
                else if(int(s[i]) == 32 && cnt==0) cnt=cnt;
                else cnt++;
            }
            return cnt;
        }
    };
    
    
FYI: Standard ASCII Code Table
