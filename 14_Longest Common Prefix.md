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

找這題是要找每個單字從前面開始看，一樣的字母，且要連續。  

ex. **fl**ower、**fl**ow、**fl**ight  


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
		    //從strs的第一個單字(""內的字)裡的第一個字母開始檢查
		    char c = strs[0][i];
		    for(int j = 0;j < strs.size();j++)
		    {
			//從每個strs單字的第一個字母比對是否一樣
			//若檢查到不一樣，直接回傳temp
			if(strs[j][i]!=c)
			{
			    return temp;
			}
		    }
		    //一樣則push到char c裡面
		    temp.push_back(c); 
		}
		return temp;
	    }
	};
```


