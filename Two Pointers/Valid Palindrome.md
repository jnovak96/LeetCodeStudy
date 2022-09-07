#flashcards 
## Description
A phrase is a **palindrome** if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.
Given a string `s`, return `true` _if it is a **palindrome**, or_ `false` _otherwise_.
## Example
```
**Input:** s = "A man, a plan, a canal: Panama"
**Output:** true
**Explanation:** "amanaplanacanalpanama" is a palindrome.
```
?
## Store string and use array flip
**TC:** ``O(n)
**SC:** ``O(n) 
1. Create a new string
2. iterate through the given string, for each character: check if the character is alphanumeric
3. If the character is alphanumeric, add it to the new string
4. compare the new string to itself but flipped and see if they are the same
## Two Pointers with custom AlphaNum Function (Better Solution)
**TC:** ``O(n)
**SC:** ``O(1) 
1. Initialize the pointers, one will start at beginning of string, one at the end
2. While the left pointer has not crossed the right pointer
	1. Check if the pointers are alphanumeric, if not skip the character
	2. When both characters are alphanumeric, check to see if they match. If not, return false.
3. If all characters match, return true
## Code
```python
class Solution:
    def isPalindrome(self, s: str) -> bool:
        l, r = 0, len(s) - 1
        while l < r:
            while l < r and not self.alphanum(s[l]):
                l += 1
            while l < r and not self.alphanum(s[r]):
                r -= 1
            if s[l].lower() != s[r].lower():
                return False
            l += 1
            r -= 1
        return True

    # Could write own alpha-numeric function
    def alphanum(self, c):
        return (
            ord("A") <= ord(c) <= ord("Z")
            or ord("a") <= ord(c) <= ord("z")
            or ord("0") <= ord(c) <= ord("9")
        )

```


