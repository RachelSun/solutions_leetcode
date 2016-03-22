# 13.Roman to Integer
**Problem:**

Given a roman numeral, convert it to an integer.
Input is guaranteed to be within the range from 1 to 3999.

**Information:**

From WIKI. Here is the link:
Roman numerals, as used today, are based on seven symbols:[1]

I:1

V:5

X:10

L:50

C:100

D:500

M:1,000

I placed before V or X indicates one less, so four is IV (one less than five) and nine is IX (one less than ten)
X placed before L or C indicates ten less, so forty is XL (ten less than fifty) and ninety is XC (ten less than a hundred)
C placed before D or M indicates a hundred less, so four hundred is CD (a hundred less than five hundred) and nine hundred is CM (a hundred less than a thousand)

Symbols are placed from left to right in order of value, starting with the largest. However, in a few specific cases,[2] to avoid four characters being repeated in succession, subtractive notation is often used as follows:

**My Solutions:**

Date: March 18, 2016

    class Solution {
    public:
        int romanToInt(string s) {
            map<char, int> rnum;
            rnum['I'] = 1;
            rnum['V'] = 5;
            rnum['X'] = 10;
            rnum['L'] = 50;
            rnum['C'] = 100;
            rnum['D'] = 500;
            rnum['M'] = 1000;
            std::string::iterator iter;
            // The end of the string is '/0'
            iter = s.end()-1;
            int sum =rnum[*iter];
            for(iter = s.end()-2; iter>=s.begin(); --iter){
                if(rnum[*iter]>= rnum[*(iter+1)]){
                    sum = rnum[*iter]+sum;
                }
                else{
                    sum = sum -rnum[*iter];
                }
            }
            return sum;
        }
    };

