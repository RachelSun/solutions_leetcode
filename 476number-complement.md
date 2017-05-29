Given a positive integer, output its complement number. The complement strategy is to flip the bits of its binary representation.

**Note:**

1. The given integer is guaranteed to fit within the range of a 32-bit signed integer.
2. You could assume no leading zero bit in the integer’s binary representation.

Solutions:

```
   C++

#include &lt;math.h&gt;
class Solution {
   public:
   int findComplement(int num) {
       int comp = 0;
       int power = 0;
       while(num/2){
           if(num%2 == 0){
               comp = 1*pow(2,power)+comp;
           }
           num/=2;
           power+=1;    
        }
        return comp;
    }
};
```



