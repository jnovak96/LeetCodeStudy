#flashcards 
## Description
Given an integer array `nums` and an integer `k`, return _the_ `k` _most frequent elements_. You may return the answer in **any order**.
## Example
```
**Input:** nums = [1,1,1,2,2,3], k = 2
**Output:** [1,2]
```
?
## Hashmap Method (Bucket Sort)
**TC:** ``O(n)
**SC:** ``O(n) 
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
    def topKFrequent(self, nums: List[int], k: int) -> List[int]:
        count = {} #hashmap to count the occurence of each value
        freq = [[] for i in range(len(nums) + 1)] # array where each index indicates the occurence of a value, stores an array of values that occur i times at each index
        
        for n in nums:
            count[n] = 1 + count.get(n, 0)
        for n, c in count.items():
            freq[c].append(n)
        result = []
        for i in range(len(freq) -1, 0, -1):
            for n in freq[i]:
                result.append(n)
                if len(result) == k:
                    return result```

![[Pasted image 20220830170013.png]]