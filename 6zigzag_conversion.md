# 6.ZigZag Conversion

** Problem:**

The string "PAYPALISHIRING" is written in a zigzag pattern on a given number of rows like this: (you may want to display this pattern in a fixed font for better legibility)

    P   A   H   N
    A P L S I I G
    Y   I   R

And then read line by line: "PAHNAPLSIIGYIR"

Write the code that will take a string and make this conversion given a number of rows:

    string convert(string text, int nRows);

convert("PAYPALISHIRING", 3) should return "PAHNAPLSIIGYIR". 


**My Solutions:**

Date: April 06, 2016


    // **20 ms**
    // Multiple places can be improved.
    
    class Solution {
    public:
        string convert(string s, int numRows) {
            int sl = s.length();
            // empty string 
            if(sl== 0 || numRows == 1) return s;

            // This is tricky
            int numCols = s.length()/(numRows-1)+1;

            char temp[numCols][numRows];
            string result;
            int cnt = 0;

            if(numRows == 2){
                for(int i = 0; i< numCols; i++){
                        for(int j = 0; j<numRows; j++){
                            if(cnt<sl){
                                temp[i][j] = s[cnt];
                                cnt++;
                            } 
                            else temp[i][j] = ' ';
                        }
                 }
            }

            if(numRows >2){
                for(int i = 0; i< numCols; i++){
                    if(i%2==0){
                        for(int j = 0; j<numRows; j++){
                            if(cnt<sl){
                                temp[i][j] = s[cnt];
                                cnt++;
                                } 
                            else temp[i][j] = ' ';
                        }
                    }
                    else{
                        for(int j = numRows-1; j>=0; j--){
                           if(cnt<sl){
                                if(j == numRows-1 || j == 0) temp[i][j] = ' ';
                                else {
                                    temp[i][j] = s[cnt];
                                    cnt++;
                                }
                           } 
                           else temp[i][j] = ' ';
                        }
                    }
                }
            }
            for(int i = 0; i< numRows; i++){
                for(int j = 0; j<numCols; j++){
                    if(temp[j][i] == ' ') continue;
                    else{
                      result.insert(result.end(), temp[j][i]);
                    }
                }
            }
            return result;
        }
    };