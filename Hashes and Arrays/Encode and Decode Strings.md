#flashcards 
## Description
Design an algorithm to encode a list of strings to a string. The encoded string is then sent over the network and is decoded back to the original list of strings.
## Example
```
Input: ["lint","code","love","you"]
Output: ["lint","code","love","you"]

Explanation:
One possible encode method is: "lint:;code:;love:;you
```
?
## Array Method
Encode strings in format (length)#(string). Decode by checking length value and parsing chars after delimeter "#".
## Code
```python
class Solution:
    def encode(self, strs):
        encodedString = ""
        for s in strs:
            encodedString += str(len(s)) + '#' + s
        return encodedString      

    def decode(self, str):
        result, i = [], 0
        while i < len(str):
            j = i
            while str[j] != "#":
                j += 1
            length = int(str[j-1])
            result.append(str[j + 1 : j + 1 + length])
            i = j + 1 + length
        return result
        # write your code here
```

