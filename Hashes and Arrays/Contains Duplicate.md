#flashcards 
Given an integer array `nums`, return `true` if any value appears **at least twice** in the array, and return `false` if every element is distinct.
?
`HashSet` store each value and check for duplicates - O(n) time and memory
```c++

bool containsDuplicate(vector<int>& nums) {
        unordered_set <int> set;
        for (int i = 0; i < nums.size(); i++)
        {
            if (set.find(nums[i]) != set.end())
            {
                return true;
            }
            else
            {
                set.insert(nums[i]);
            }
        }
        return false;
    }
    ```
