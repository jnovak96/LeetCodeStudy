#flashcards
Given two strings `s` and `t`, return `true` _if_ `t` _is an anagram of_ `s`_, and_ `false` _otherwise_.
``**Input:** s = "anagram", t = "nagaram"
``**Output:** true
?
## Hashmap Method
Use 2 `hashmaps` to store the frequency of each char in each string
```c++
unordered_map<char, int> mapS;
unordered_map<char, int> mapT;
for (int i = 0; i < s.size(); i++)
{
	//count chars
}
return mapS == mapT;
```
## Sort and compare method
Or you can sort and compare
```c++
bool isAnagram(string s, string t) {
        if(s.length()!=t.length())
        {
            return false;
        }
        sort(s.begin(),s.end());
        sort(t.begin(),t.end());
        return s==t;
    }
```
<!--SR:!2022-09-02,1,230-->