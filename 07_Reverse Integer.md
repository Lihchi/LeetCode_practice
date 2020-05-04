## 7. Reverse Integer

Given a 32-bit signed integer, reverse digits of an integer.

Example 1:
Input: 123
Output: 321

Example 2:
Input: -123
Output: -321

Example 3:
Input: 120
Output: 21

Note:  
Assume we are dealing with an environment which could only store integers within   
the 32-bit signed integer range: [−231,  231 − 1].  
For the purpose of this problem, assume that your function returns 0   
when the reversed **integer overflows**.  

C++：  
```c++
    class Solution {
    public:
        int reverse(int x) {

            long long num = 0;
            int n = 0;
            while (x)
            {
                n = x % 10;
                num = n + num * 10;
                x /= 10;
            }
            return (num>INT_MAX||num<INT_MIN)? 0 : num;	
        }
    };
```
INT_MAX：int的最大值  
            --->2147483647  
INT_MIN：int的最小值  
            --->-2147483647 - 1  
