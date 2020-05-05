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

---  

### code使用到的stack

- Stack 是一種 先進後出 FILO 的資料結構  
- 使用stack需要include名為stack特殊標頭檔：  
```c++
	#include <stack>
```
- 基本宣告：stack<儲存變數型態>  Stack名稱; 
```c++
	stack<int> stack_int;               // 儲存int形態的stack
	stack<char> stack_char;             // 儲存char型態
	stack<string> stack_string;         // 儲存string型態
	stack< stack<int> > stack_stack_int;// 當然也可以在stack裡面儲存stack;
```
- 基本操作：  
| 函數名稱| 說明 |
| :-------------:|:-------------:|
| push()| 將資料放進Stack頂端 |
| top() | 回傳最上方的資料 |
| pop() | 移除最上方的資料 |
| empty() | 回傳stack是否為空  1: 空  0: 有資料 |
| size() | 回傳stack目前有幾筆資料 |

