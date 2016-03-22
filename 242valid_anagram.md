# 242.Valid Anagram


**Problem:**

Given two strings s and t, write a function to determine if t is an anagram of s.

For example,

s = "anagram", t = "nagaram", return true.s = "rat", t = "car", return false.

You may assume the string contains only lowercase alphabets.

**My Solutions:**

Date: March 18, 2016

    class Solution {
    public:
        bool isAnagram(string s, string t) {
            if(s.length()!= t.length()){
                return false;
            }
            int re = 0;
            sort(s.begin(), s.end());
            sort(t.begin(), t.end());
            for(int i =0; i< s.length();i++){
                if(s[i] != t[i])
                return false;
            }
            return true;
        }
    };

