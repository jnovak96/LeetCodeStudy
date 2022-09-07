#flashcards 
## Description
Given an integer array `nums`, return _an array_ `answer` _such that_ `answer[i]` _is equal to the product of all the elements of_ `nums` _except_ `nums[i]`.
The product of any prefix or suffix of `nums` is **guaranteed** to fit in a **32-bit** integer.
You must write an algorithm that runs in `O(n)` time and without using the division operation.
## Example
```
**Input:** nums = [1,2,3,4]
**Output:** [24,12,8,6]
```
?
## Pass Through Array Twice Method
**TC:** ``O(n)
**SC:** ``O(1) 
1. Pass through nums array from 0-3, multiply each number by previous to get prefix
2. Store the prefix products in the result array
3. Pass through nums array backwards, multiply result at index by postfix
	1. calculate new postfix by multiplay prev postfix by nums[i]
4. Return result
```python
class Solution:
    class Solution:
    def productExceptSelf(self, nums: List[int]) -> List[int]:
        result = [1] * len(nums)
        
        pre = 1
        for i in range(len(nums)):
            result[i] = pre
            pre *= nums[i]
                    
        post = 1
        for i in range(len(nums) -1, -1, -1):
            result[i] *= post
            post *= nums[i]
        return result            
```
<!--SR:!2022-09-04,3,250-->

![[Pasted image 20220901152312.png]]![[Pasted image 20220901162433.png]]