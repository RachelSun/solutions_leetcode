# 165.Compare Version Numbers

**Problem:**

Compare two version numbers version1 and version2.

    If version1 > version2 return 1, 
    if version1 < version2 return -1, 
    otherwise return 0.

You may assume that the version strings are non-empty and contain only digits and the . character.

The . character does not represent a decimal point and is used to separate number sequences.

Here is an example of version numbers ordering:

0.1 < 1.1 < 1.2 < 13.37


** My Solutions:**

Date: April 06, 2016


    // **0ms**
    // This is definitely not a good solution.
    class Solution {
    public:
        int compareVersion(string version1, string version2) {
            
            int l1 = version1.length();
            int l2 = version2.length();
            
            /* The leetcode does not need you to check whether the strings are empty or not.
            if(l1 == 0 && l2 == 0) return 0;
            if(l1 == 0) return -1;
            if(l2 == 0) return 1;
            */
  
            // Create two vectors to store all the version numbers
            // 1.12.13 will be stored as 1, 12, 13
            
            vector<int> num1; // for version1
            vector<int> num2; // for version2

            int temp = 0;

            for(int i = 0; i<= l1; i++){
                if(version1[i] == '.' || i == l1) {
                    // If come up with a "." or the end of the string
                    // Store the number.
                    num1.push_back(temp);
                    temp = 0;
                    continue;
                }
                    // change from string to integer
                    // -48 ASCII 0 -> 48
                    temp= temp*10+version1[i]-48;
            }

            for(int i = 0; i<= l2; i++){
                if(version2[i] == '.' || i == l2) {
                    num2.push_back(temp);
                    temp = 0;
                    continue;
                }
                    temp= temp*10+version2[i]-48;
            }
            
            // Add extra 0 for the short version to make the length of both version number equal
            // 1.12 and 1.12.13 will be: 1,12,0 and 1,12,13
            
            int cnt = num1.size()-num2.size(); 
            while(cnt>0){
                num2.push_back(0);
                cnt--;
            }
            while(cnt<0){
                num1.push_back(0);
                cnt++;
            }
            //Compare each number from two vectors.
            int i = 0;
            while(i<num1.size()){
                if(num1[i] > num2[i]) return 1;
                if(num1[i] < num2[i]) return -1;
                if(num1[i] == num2[i]) i++;
            }
            return 0;
        }
    };