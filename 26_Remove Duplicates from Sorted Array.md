## 26. Remove Duplicates from Sorted Array
Given a sorted array nums, remove the duplicates in-place such that each element appear only once and return the new length.  

Do not allocate extra space for another array, you must do this by modifying the input array in-place with O(1) extra memory.  

Example 1:   
Given nums = [1,1,2],  

Your function should return length = 2, with the first two elements of nums being 1 and 2 respectively.  

It doesn't matter what you leave beyond the returned length.  

Example 2:  
Given nums = [0,0,1,1,1,2,2,3,3,4],  

Your function should return length = 5, with the first five elements of nums being modified to 0, 1, 2, 3, and 4 respectively.  

It doesn't matter what values are set beyond the returned length.  

Solution：  
i是慢指標,j是快指標
i跟他之後的數去做比較：
> - 若一樣，則j++繼續跑
> - 若不同，則i往後一個

ex,  
原本：

| i |   |   |
|:-:|:-:|:-:|
| 1 | 1 | 2 |
|   | j |   |

i跟j的值相同

j++後：  

|---|---|---|
|i| | |
|1|1|2|
| | |**j**|

i != j，  
i++  

|---|---|---|
| |**i**| |
|1|1|2|
| | |j|

現在i指的的值要被j指的值取代

|---|---|---|
| |i| |
|1|**2**|2|
| | |j|


C++：  
```c++
    class Solution {
		public:
			int removeDuplicates(vector<int>& nums) {
			if(nums.empty()) return 0;
			int i=0;
			for(int j=1;j<nums.size();j++)
			{
				if(nums[j]!=nums[i])
				{   
					i++;
					nums[i]=nums[j];
					//遇到不同的就把j的值向前移一個
				}
			}
			return i+1;
		}
	};
```


