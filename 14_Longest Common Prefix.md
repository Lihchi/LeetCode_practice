## 14. Longest Common Prefix

Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string "".

Example 1:  
	Input: ["flower","flow","flight"]  
	Output: "fl"  

Example 2:  
	Input: ["dog","racecar","car"]  
	Output: ""  
	Explanation: There is no common prefix among the input strings.    
  
Note:  
All given inputs are in lowercase letters a-z.  


C++：  
```c++
    class Solution {
	public:
		string longestCommonPrefix(vector<string>& strs) {
			if(strs.empty())
			{
				return "";
			}
			string temp = "";
			for(int i =0;i<strs[0].size();i++)
			{
				char c = strs[0][i];
				for(int j=0;j<strs.size();j++)
				{
					if(strs[j][i]!=c)
					{
						return temp;
					}
				}
			   temp.push_back(c); 
			}
			return temp;
		}
	};
```


