#flashcards 
## Description
Given a string `s`, find the length of the **longest substring** without repeating characters.
## Example
```
**Input:** s = "abcabcbb"
**Output:** 3
**Explanation:** The answer is "abc", with the length of 3.
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
    class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        charSet = set()
        l = 0
        maxLength = 0
        
        for r in range(len(s)):
            while s[r] in charSet:
                charSet.remove(s[l])
                l += 1
            charSet.add(s[r])
            maxLength = max(maxLength, len(charSet))
        return maxLength
```
![[Pasted image 20220907181155.png]]