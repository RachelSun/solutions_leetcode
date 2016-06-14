# 345.Reverse Vowels of a String

**Problem:**
Write a function that takes a string as input and reverse only the vowels of a string.

    Example 1:
    Given s = "hello", return "holle".

    Example 2:
    Given s = "leetcode", return "leotcede".
    
    
    
** My Solutions:**

Date: June 14, 2016

        // An incorrect solution. 
        // There is one example "race car" -> "race car"
        
        // Fine, I did not learn English well...


        class Solution {
        public:
            string reverseVowels(string s) {
                int sl = s.length();
                char c[sl];
                int idx[sl];
                int cnt = 0;
                for(int i = 0; i<sl; i++){
                      if(s[i] =='a' || s[i] == 'e' || s[i] == 'i'|| s[i] == 'o'||s[i] == 'u' 
                      || s[i] =='A' || s[i] == 'E' || s[i] == 'I'|| s[i] == 'O'||s[i] == 'U'){
                        c[cnt] = s[i];
                        idx[cnt] = i;
                        cnt++;
                    }
                }

                cout<< c[0]<< c[1]<<endl;
                if(cnt<2) return s;
                s[idx[cnt-1]] = s[idx[0]];
                for(int i = 0; i<cnt-1;i++){
                    s[idx[i]] = c[i+1];
                }
                return s;
            }
        };