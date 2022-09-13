#flashcards 
## Description
Given the roots of two binary trees `p` and `q`, write a function to check if they are the same or not.
Two binary trees are considered the same if they are structurally identical, and the nodes have the same value.
## Example
```
**Input:** p = [1,2,3], q = [1,2,3]
**Output:** true
```
?
## Recursive Depth First Search Solution
**TC:** ``O(n)
Use recursion to check if the left child node of tree A == left child node of tree B, then if the  right child node of tree A == right child node of tree B
## Code
```python
class Solution:
    def isSameTree(self, p: Optional[TreeNode], q: Optional[TreeNode]) -> bool:
        if not p and not q:
            return True
        if p and q and p.val == q.val:
            return self.isSameTree(p.left, q.left) and self.isSameTree(p.right, q.right)
        else:
            return False```


