## 20. Valid Parentheses

Given a string containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.  
  
An input string is valid if:  
  
- Open brackets must be closed by the same type of brackets.
- Open brackets must be closed in the correct order.  
  
Note that an empty string is also considered valid.

Example 1:  
Input: "()"  
Output: true  

Example 2:  
Input: "()[]{}"  
Output: true  

Example 3:  
Input: "(]"  
Output: false  

Example 4:  
Input: "([)]"  
Output: false  

Example 5:  
Input: "{[]}"  
Output: true  


C++：  
```c++
    class Solution {
	public:
		bool isValid(string s) {
			stack< char > mystack;
			for(int i = 0;i<s.size();i++)
			{
				if(s[i] == '(' || s[i] == '[' || s[i] == '{')
				{
					mystack.push(s[i]);//將資料放進Stack頂端
				}
				else
				{
					if(mystack.empty())//stack 是空的 ->沒有左邊的括號
					{
						return false;
					}
					if(s[i]==')' && mystack.top() != '(')
					{
						return false;
					}
					if(s[i]==']' && mystack.top() != '[')
					{
						return false;
					}
					if(s[i]=='}' && mystack.top() != '{')
					{
						return false;
					}
					mystack.pop();//若上面都不符合，移除最上方資料
				}
			}
			return mystack.empty();
			//所有字符都判斷處理過後，stack應為空，否則則無效
		}
	};
```

