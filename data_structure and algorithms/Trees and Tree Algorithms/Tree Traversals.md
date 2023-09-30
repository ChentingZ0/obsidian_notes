which order to visit all the nodes.
Three traversals: preorder, inorder, postorder

```
# recursive way to write preorder
def preorder(tree):
	if tree:
		print(tree.getRootVal())
		preorder(tree.getLeftChild())
		preorder(tree.getRightChild())
```