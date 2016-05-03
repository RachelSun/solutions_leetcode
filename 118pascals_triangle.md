# 118.Pascal's Triangle

** Problem:**
Given numRows, generate the first numRows of Pascal's triangle.

For example, given numRows = 5,
Return

    [
         [1],
        [1,1],
       [1,2,1],
      [1,3,3,1],
     [1,4,6,4,1]
    ]
    
** My Solutions:**

Date: May 3, 2016

    class Solution {
    public:
        vector<vector<int>> generate(int numRows) {
            vector<vector<int>> vec;
            for(int i = 0; i< numRows; i++){
                vector<int> temp (i+1,1);
                vec.push_back(temp);
            }
            for(int i = 2; i<numRows; i++){
                for(int j = 1; j<i; j++){
                    vec[i][j] = vec[i-1][j]+vec[i-1][j-1];
                }
            }
            return vec;
        }
    };