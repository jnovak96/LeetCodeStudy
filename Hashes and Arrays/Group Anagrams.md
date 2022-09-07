#flashcards 
## Description
Given an array of strings `strs`, group **the anagrams** together. You can return the answer in **any order**.
An **Anagram** is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.
## Example
```
Input: strs = ["eat","tea","tan","ate","nat","bat"]
Output: [["bat"],["nat","tan"],["ate","eat","tea"]]
```
?
## Hashmap Method
**TC:** ``O(m*n)
**SC:** ``?? 
1. Create a hashmap to map the count of each character to the list of anagrams
2. Loop through the strings
	1. create count array to count occurence of each char
	2.  loop through chars
		1. If a char appears, add 1 to value at the char's index in count
	3. Add the string to the hashmap based on it's count as index ``tuple(count):string 
3. return the results 
## Code
```python
class Solution:
    def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        result = defaultdict(list) # map charCount to list of anagrams
        
        for s in strs:
            count = [0] * 26 #a, ..., z
            for c in s:
                count[ord(c) - ord("a")] += 1 # ord(c) - ord("a") gets index
            result[tuple(count)].append(s) # add the current string to index of hashmap with corresponding count array
        return result.values()
```
<!--SR:!2022-09-05,4,270-->

