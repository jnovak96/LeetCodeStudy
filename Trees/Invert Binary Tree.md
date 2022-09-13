#flashcards 
## Description
Given the `root` of a binary tree, invert the tree, and return _its root_.
## Example
```
**Input:** root = [4,2,7,1,3,6,9]
**Output:** [4,7,2,9,6,3,1]
```
?
## Recursive Depth First Search Solution
**TC:** ``??
**SC:** ``?? 
Swap the two children of the root and then recursively call the function passing the left child and then the right child.
## Diagram
![[invert1-tree.jpg]]
## Code
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def invertTree(self, root: TreeNode) -> TreeNode:
        if not root:
            return None

        # swap the children
        tmp = root.left
        root.left = root.right
        root.right = tmp

        self.invertTree(root.left)
        self.invertTree(root.right)
        return root
```


