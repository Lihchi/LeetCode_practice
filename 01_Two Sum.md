## 1. Two Sum

Given an array of integers, return indices of the two numbers such that they add up to a specific target.  
  
You may assume that each input would have exactly one solution, and you may not use the same element twice.  

Example :  
Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].


C++：  
```c++
    class Solution {
	public:
		vector<int> twoSum(vector<int>& nums, int target) {
			vector<int> n;        
			int t = target;
			for(int i=0;i<nums.size();i++)
			{
				for(int j = i+1 ; j < nums.size() ; j++)
				{
					if(nums[i] + nums[j] == t)
					{
						n.push_back(i);
						n.push_back(j);
					}
				}
			}
			return n;
		}
	};
```
 javascript：
 ```javascript
 /**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
    var n = []//宣告一個空陣列 n
    var t = target
    for(var i =0;i<nums.length;i++)//lenght不用加"()"
    {
           for(var j = i+1;j<nums.length;j++)
           {
                   if(nums[i]+nums[j]==t)
                   {
                      n.push(i);
                      n.push(j);
                    }
           }
     }
    return n
};
```
