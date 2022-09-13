#flashcards 
Given an integer array `nums`, return `true` if any value appears **at least twice** in the array, and return `false` if every element is distinct.
?
## Hashset Solution
Run through array and check if each value is in the set. Add the value to the set if it does not already exist.
## Diagram
![[Pasted image 20220911015655.png]]
## Code
```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        hashset = set()

        for n in nums:
            if n in hashset:
                return True
            hashset.add(n)
        return False
```    ```
