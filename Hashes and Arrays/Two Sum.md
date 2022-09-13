#flashcards 
Given an array of integers `nums` and an integer `target`, return _indices of the two numbers such that they add up to `target`_.
You may assume that each input would have **_exactly_ one solution**, and you may not use the _same_ element twice.
You can return the answer in any order.
## Example
**Input:** nums = [2,7,11,15], target = 9
**Output:** [0,1]
**Explanation:** Because nums[0] + nums[1] == 9, we return [0, 1].
?
## Hashmap Solution
Use a hashmap to track previously seen values and their indexes. Check values to see if the difference exists in the hashmap.
## Instructions
1. Loop through array
2. calculate difference of target value minus current element
3. check if the difference is in the hashmap (difference + current would be the solution)
	1. if it is, return solution
	2. if not, continue
4. add the element to the hashmap and repeat
## Diagram
![[Pasted image 20220911012815.png]]
## Code
```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        hashmap = {} #val:index
        
        for i, n, in enumerate(nums):
            diff = target - n
            if diff in hashmap:
                return [hashmap[diff], i]
            hashmap[n] = i
        return
```
