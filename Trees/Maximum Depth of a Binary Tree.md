#flashcards 
## Description
Given the `root` of a binary tree, return _its maximum depth_.
A binary tree's **maximum depth** is the number of nodes along the longest path from the root node down to the farthest leaf node.
## Example
![[tmp-tree.jpg]]
```
**Input:** root = [3,9,20,null,null,15,7]
**Output:** 3
```
**Input:** root = [3,9,20,null,null,15,7]
**Output:** 3
?
## Recursive Depth First Search Solution
**TC:** ``O(n)
Use recursion to return 1 + the max result of the function on the two children.
## Iterative Depth First Search Solution
**TC:** ``O(n)
Use depth first search to count the depth of each path on the tree. Track with a stack.
## Iterative Breadth First Search Solution
**TC:** ``O(n)
Use breadth first search to count the number of levels in the tree. Track with a queue.
## Diagram

## Code
```python
# RECURSIVE DFS
class Solution:
    def maxDepth(self, root: TreeNode) -> int:
        if not root:
            return 0

        return 1 + max(self.maxDepth(root.left), self.maxDepth(root.right))


# ITERATIVE DFS
class Solution:
    def maxDepth(self, root: TreeNode) -> int:
        stack = [[root, 1]]
        res = 0

        while stack:
            node, depth = stack.pop()

            if node:
                res = max(res, depth)
                stack.append([node.left, depth + 1])
                stack.append([node.right, depth + 1])
        return res

# BFS
class Solution:
    def maxDepth(self, root: TreeNode) -> int:
        q = deque()
        if root:
            q.append(root)

        level = 0

        while q:

            for i in range(len(q)):
                node = q.popleft()
                #check if nodes are not null
                if node.left:
                    q.append(node.left)
                if node.right:
                    q.append(node.right)
            level += 1
        return level
```
```
```


