Binary search tree is a special kind of binary tree.

**Balanced search trees**: We call the tree is balanced which means the heights of left and right sub-trees is not greater than 1.

Node-based binary tree data structure:
- The left subtree of a node contains only nodes with keys lesser than the node's key.
- The right subtree of a node only contains nodes with keys greater than the node's key.
- The left and right subtree must also be a binary search tree.
![binary search tree](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20221215114732/bst-21.png)

Search, insert, or delete in a binary search tree in $O(log(n))$ time in average case.
```python
 class TreeNode:
	 def __init__(self, x):
		  self.val = x
		  self.left = None
		  self.right = None
```
In the above case:
$root = [8,3,10,1,6,null,14,null,null,4,7,13,null]$
### Implementation

[Kth smallest Element in a BST](https://leetcode.com/problems/kth-smallest-element-in-a-bst/submissions/)
[Lowest Common Ancestor of a Binary Tree](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree/)
