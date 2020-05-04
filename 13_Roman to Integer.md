## 13. Roman to Integer

Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.  

| Symbol | Value |
| :---: | :----: |
| I | 1 |
| V | 5 |
| X | 10 |
| L | 50 |
| C | 100 |
| D | 500 |
| M | 1000 |
  
Example：  
I can be placed before V (5) and X (10) to make 4 and 9.  
X can be placed before L (50) and C (100) to make 40 and 90.  
C can be placed before D (500) and M (1000) to make 400 and 900.  


Example 1:  
Input: "III"
Output: 3

Example 2:  
Input: "IV"
Output: 4

Example 3:  
Input: "IX"
Output: 9

Example 4:  
Input: "LVIII"
Output: 58
Explanation: L = 50, V= 5, III = 3.

Example 5:  
Input: "MCMXCIV"
Output: 1994
Explanation: M = 1000, CM = 900, XC = 90 and IV = 4.

C++：  
```c++
    class Solution {
	public:
		int romanToInt(string s) {
			int num = 0;//output value
			//陣列順序由左邊先開始
			for(int i =0;i<s.size();i++)
			{
				if (s[i] == 'I') num += 1;
				if (s[i] == 'V') num += 5;
				if (s[i] == 'X') num += 10;
				if (s[i] == 'L') num += 50;
				if (s[i] == 'C') num += 100;
				if (s[i] == 'D') num += 500;
				if (s[i] == 'M') num += 1000;
				
				//原本IV-->num == 6,正確答案是num == 4
				//原本IX-->num == 11,正確答案是num == 9
				//差2
				if(i>0  && (s[i-1]=='I') && (s[i] == 'V' || s[i] == 'X'))
				{
					num -= 2;
				}
				//原本XL-->num == 60,正確答案是num == 40
				//原本XC-->num == 110,正確答案是num == 90
				//差20
				if(i>0 && (s[i-1]=='X') && (s[i]=='L' || s[i] == 'C'))
				{
					num -= 20;
				}
				//原本CD-->num == 600,正確答案是num == 400
				//原本CM-->num == 1100,正確答案是num == 900
				//差200
				if(i>0  && (s[i-1]=='C') && (s[i]=='D' || s[i] == 'M'))
				{
					num -= 200;
				}
			}
			return num;
		}
	};
```

