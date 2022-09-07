#flashcards 
## Description
Given an integer array nums, return all the triplets `[nums[i], nums[j], nums[k]]` such that `i != j`, `i != k`, and `j != k`, and `nums[i] + nums[j] + nums[k] == 0`.
Notice that the solution set must not contain duplicate triplets.
## Example
```
**Input:** nums = [-1,0,1,2,-1,-4]
**Output:** [[-1,-1,2],[-1,0,1]]
**Explanation:** 
nums[0] + nums[1] + nums[2] = (-1) + 0 + 1 = 0.
nums[1] + nums[2] + nums[4] = 0 + 1 + (-1) = 0.
nums[0] + nums[3] + nums[4] = (-1) + 2 + (-1) = 0.
The distinct triplets are [-1,0,1] and [-1,-1,2].
Notice that the order of the output and the order of the triplets does not matter.
```
?
## Sort then use two pointers (like Two Sum II)
**TC:** ``??
**SC:** ``?? 
1. Sort the array
2. Iterate throught the array and for each value use left and right pointers to find a sum that equals zero
3. if the sum is greater than zero, iterate right pointer -1
4. if sum is less than zero iterate left pointer +1
5. if sum equals zero, add the current value, value at left pointer, and value at right pointer to a list and add the list to the result.

## Code
```python
class Solution:
        def threeSum(self, nums: List[int]) -> List[List[int]]:
        res = []
        nums.sort()
        
        for i, a in enumerate(nums):
	        #Check if it is first value or duplicate value
            if i > 0 and a == nums[i-1]:
                continue
                
            l, r = i + 1, len(nums) - 1
            while l < r:
                threeSum = a + nums[l] + nums[r]
                if threeSum > 0:
                    r -= 1
                elif threeSum < 0:
                    l += 1
                else:
                    res.append([a, nums[l], nums[r]])
                    l += 1
                    #shift left pointer to avoid duplicates
                    while nums[l] == nums[l - 1] and l < r:
                        l += 1
        return res
    
```


