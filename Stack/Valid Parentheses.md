#flashcards 
## Description
Given a string `s` containing just the characters `'('`, `')'`, `'{'`, `'}'`, `'['` and `']'`, determine if the input string is valid.
An input string is valid if:
1.  Open brackets must be closed by the same type of brackets.
2.  Open brackets must be closed in the correct order.
3.  Every close bracket has a corresponding open bracket of the same type.
## Example
```
**Input:** s = "()"
**Output:** true
**Input:** s = "()[]{}"
**Output:** true
```
?
## Stack Method
**TC:** ``O(n)
**SC:** ``?? 
1. Map each left parenthese to the right parenthese with a hashmap
2. iterate through the string and check if the character is in the map
3. if it is, check if it corresponds to the last value added to the stack
4. if not, the parentheses order is messed up, return false
5. else return true
## Code
```python
class Solution:
    def isValid(self, s: str) -> bool:
        Map = {")": "(", "]": "[", "}": "{"}
        stack = []

        for c in s:
            if c not in Map:
                stack.append(c)
                continue
            if not stack or stack[-1] != Map[c]:
                return False
            stack.pop()

        return not stack
```
![[Pasted image 20220909021556.png]]