#flashcards
Given two strings `s` and `t`, return `true` _if_ `t` _is an anagram of_ `s`_, and_ `false` _otherwise_.
``**Input:** s = "anagram", t = "nagaram"
``**Output:** true
?
## Hashmap Solution
Use two hashmaps to store the count of each character in the string. Compare the two maps to see if they are equal.
## Diagram
![[Pasted image 20220911014636.png]]
## Code
```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        if len(s) != len(t):
            return False

        countS, countT = {}, {}

        for i in range(len(s)):
            countS[s[i]] = 1 + countS.get(s[i], 0)
            countT[t[i]] = 1 + countT.get(t[i], 0)
        return countS == countT
```
<!--SR:!2022-09-02,1,230-->
