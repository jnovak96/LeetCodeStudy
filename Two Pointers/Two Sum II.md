#flashcards 
## Description
Given a **1-indexed** array of integers `numbers` that is already **_sorted in non-decreasing order_**, find two numbers such that they add up to a specific `target` number. Let these two numbers be `numbers[index1]` and `numbers[index2]` where `1 <= index1 < index2 <= numbers.length`.
Return _the indices of the two numbers,_ `index1` _and_ `index2`_, **added by one** as an integer array_ `[index1, index2]` _of length 2._
The tests are generated such that there is **exactly one solution**. You **may not** use the same element twice.
Your solution must use only constant extra space.
## Example
```
**Input:** numbers = [2,7,11,15], target = 9
**Output:** [1,2]
**Explanation:** The sum of 2 and 7 is 9. Therefore, index1 = 1, index2 = 2. We return [1, 2].
```
?
## Method 1
**TC:** ``??
**SC:** ``?? 
1. Step 1
2. Step 2
3. Step 3
## Method 2
**TC:** ``??
**SC:** ``?? 
1. Step 1
2. Step 2
3. Step 3
## Code
```python
class Solution:
    def twoSum(self, numbers: List[int], target: int) -> List[int]:
        i, j = 0, len(numbers) - 1
      
        while i < j:
            currentsum = numbers[i] + numbers[j]
            if currentsum > target:
                j -= 1
            elif currentsum < target:
                i += 1
            else:
                return [i+1, j+1]
            
            
```


