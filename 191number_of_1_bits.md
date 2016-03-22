# 191.Number of 1 Bits

**Problem:
**
Write a function that takes an unsigned integer and returns the number of ’1' bits it has (also known as the Hamming weight).

For example, the 32-bit integer ’11' has binary representation 00000000000000000000000000001011, so the function should return 3.

**FYI:**

C has very loose definitions on its basic integer data types (char, short, int, long, and long long). The language guarantees that they can represent at least some range of values, but any particular platform (compiler, operating system, hardware) might be larger than that.
A good example is long. On one machine, it might be 32 bits (the minimum required by C). On another, it's 64 bits.
So, what do you do if you want an integer type that's precisely 32 bits long? That's where int32_t comes in: it's an alias for whatever integer type your particular system has that is exactly 32 bits. uint32_t is the same, but for unsigned 32 bit values. On one system, that might be unsigned int and on another unsigned long.

**My Solutions:**

Date: March 21, 2016

    class Solution {
    public:
        int hammingWeight(uint32_t n) {
            int k;
            int cnt = 0;
            for (int c = 31; c >= 0; c--){
                k = n>>c;
                if (k&1)
                cnt++;
            }
            return cnt;
        }
    };

**Note:**

variable A holds 60 (0011 1100) and variable B holds 13(0000 1101):

* & : Binary AND Operator copies a bit to the result if it exists in both operands.  (A & B) will give 12 which is 0000 1100.

* | : Binary OR Operator copies a bit if it exists in either operand. (A | B) will give 61 which is 0011 1101.
 
* ^ : Binary XOR Operator copies the bit if it is set in one operand but not both. (A ^ B) will give 49 which is 0011 0001.

* ~ : Binary Ones Complement Operator is unary and has the effect of 'flipping' bits. (~A ) will give -61 which is 1100 0011 in 2's complement form due to a signed binary number.
 
* << : Binary Left Shift Operator. The left operands value is moved left by the number of bits specified by the right operand. A << 2 will give 240 which is 1111 0000.
  
* &gt;&gt; : Binary Right Shift Operator. The left operands value is moved right by the number of bits specified y the right operand. A >> 2 will give 15 which is 0000 1111.

