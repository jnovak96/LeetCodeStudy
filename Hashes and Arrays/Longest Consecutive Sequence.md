#flashcards 
## Description
Given an unsorted array of integers `nums`, return _the length of the longest consecutive elements sequence._
You must write an algorithm that runs in `O(n)` time.
## Example
```
**Input:** nums = [100,4,200,1,3,2]
**Output:** 4
**Explanation:** The longest consecutive elements sequence is `[1, 2, 3, 4]`. Therefore its length is 4.
```
?
## Set Solution
Create a set with all of the numbers in the input array. Check the elements in the array against the set to see if they have left neighbors and if they don't track the length while checking that the next value exists in the set. Return the highest length value.
## Diagram
![[Pasted image 20220912014651.png]]
## Code
```python
class Solution:
    def longestConsecutive(self, nums: List[int]) -> int:
        numSet = set(nums)
        longest = 0
        for n in nums:
            #check if value is start of a sequence
            if (n - 1) not in numSet:
                length = 0
                while (n + length) in numSet:
                    length += 1
                longest = max(length, longest)
        return longest
```
<!--SR:!2022-09-02,1,230-->

