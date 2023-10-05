Binary search tree is a special kind of binary tree.

**Balanced search trees**: We call the tree is balanced which means the heights of left and right sub-trees is not greater than 1.

Node-based binary tree data structure:
- The left subtree of a node contains only nodes with keys lesser than the node's key.
- The right subtree of a node only contains nodes with keys greater than the node's key.
- The left and right subtree must also be a binary search tree.
![binary search tree](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20221215114732/bst-21.png)

Search, insert, or delete in a binary search tree in $O(log(n))$ time in average case.

### Implementation

