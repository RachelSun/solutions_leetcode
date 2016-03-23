# 67.Add Binary

**Problem:**

Given two binary strings, return their sum (also a binary string).

For example,

    a = "11"

    b = "1"

    Return "100". 

**My Solutions:**

Date: March 23, 2016


    // This code is obviously too long... Optimazation are needed.
    
    class Solution {
    public:
        string addBinary(string a, string b) {
            int al = a.length()-1;
            int bl = b.length()-1;
            int l;
            int flag = 0;
            string sum;
            if(al>bl){
                sum = a;
                l = al;
            }
            else{
                sum = b;
                l=bl;
            } 
            while(al>=0 && bl>=0){
                if(int(a[al]) == int(b[bl])){
                    if(flag == 1 && int(b[bl])==48 ){
                        sum[l]= '1';
                        flag = 0;
                    }
                    else if(flag == 0 && int(b[bl])==49 ){
                            sum[l] = '0';
                            flag = 1;
                    }
                }
                else if(flag == 0){
                     sum[l] = '1';
                }
                else{
                    sum[l] = '0';
                    flag = 1;
                }
                al--;
                bl--;
                l--;
            }

            while(al>=0){
                if(flag == 0){
                    sum[l] = a[al];
                }
                else if(int(a[al]) == 49 && flag == 1){
                    sum[l] = '0';
                    flag = 1;
                }
                else{
                     sum[l] = '1';
                     flag = 0;
                }
                l--;
                al--;
            }
            while(bl>=0 )
            {
                if(flag == 0){
                    sum[l] = b[bl];
                }
                else if(int(b[bl]) == 49 && flag == 1){
                    sum[l] = '0';
                    flag = 1;
                }
                else{
                     sum[l] = '1';
                     flag = 0;
                }
                l--;
                bl--;
            }
            if(flag) sum.insert(sum.begin(), '1');
            return sum;
        }
    };
