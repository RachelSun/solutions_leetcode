# 205.Isomorphic Strings

**Problem:**

Given two strings s and t, determine if they are isomorphic.

Two strings are isomorphic if the characters in s can be replaced to get t.

All occurrences of a character must be replaced with another character while preserving the order of characters. No two characters may map to the same character but a character may map to itself.

    For example,
    Given "egg", "add", return true.

    Given "foo", "bar", return false.

    Given "paper", "title", return true.

    Note:
    You may assume both s and t have the same length.
    
    
 **My Solutions:**
 
     Date: March 29, 2016
        // The runtime is 56ms not good enough.
        class Solution {
        public:
            bool isIsomorphic(string s, string t) {
                map<char, char> m;
                if(s.length()!= t.length()) return false;
                if(s.length() <=1 && t.length()==s.length()) return true;
                for(int i = 0; i<s.length();i++){
                    if(m[s[i]] == NULL){
                        m[s[i]] = t[i];
                    }
                    else{
                        if(m[s[i]] != t[i]){
                            return false;
                        }
                    }
                }
                return true;
            }
        };