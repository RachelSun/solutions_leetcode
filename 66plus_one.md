# 66.Plus One
**Problem:**

Given a non-negative number represented as an array of digits, plus one to the number.

The digits are stored such that the most significant digit is at the head of the list.

**My Solutions:**

Date: March 23, 2016

    class Solution {
    public:
        vector<int> plusOne(vector<int>& digits) {
            int i = digits.size() - 1;
            while (i >= 0) {
                if (digits[i] == 9) {
                    digits[i--] = 0;
                }
                else{
                    digits[i] += 1;
                    return digits;
                }
            }
            digits[0] = 1;
            digits.push_back(0);
            return digits;
        }
    };


    Note:
    
    Like the line "digits[i--] = 0;"!
    
    



Date: March 23, 2016

    class Solution {
    public:
        vector<int> plusOne(vector<int>& digits) {
            int i = digits.size()-1;
            while(i>=0){
                if(digits[i]<9){
                    digits[i] = digits[i]+1;
                    break;
                }
                else{
                    //digits[i] = 0;
                    //i--;
                    // Modified according to the last version
                    digits[i--] = 0;
                }
                if(digits[0] == 0){
                  digits.insert(digits.begin(), 1); 
                }
            }
            return digits;
        }
    };
    

    Note:
      Starting from the last digit of the number to the first digit of the number:
    * If the last digit is not 9, then just add 1 and return the number.
      * 12+1 = 13
    * If the last digit is 9, then this digit will become 0 and the previous digit will need to add 1.
      * 199+1 = 200
    * If the number is a sequence of 9, then the number need to insert one as the new first digit.
      * 999+1 = 1000


