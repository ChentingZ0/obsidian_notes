define a class has attributes for 
root value, left subtree, right subtree.

```python
class BinaryTree:
	def __init__(self, rootObj):
		self.key = rootObj
		self.leftChild = None
		self.rightChild = None
		
	def insertLeft(self, newNode):
		if self.leftChild == None:
			self.leftCHild = BinaryTree(newNode)
		else:
			t = BinaryTree(newNode)
			t.leftChild = self.leftChild
			self.leftChild = t

	def getRightChild(self):
		return self.rightChild

	def getLeftChild(self):
		return self.leftChild

	def setRootVal(self, obj):
		self.key = obj
		
	def getRootVal(self):
		return self.key
```
###### tip:
The attributes `left` and `right` will become references to other instances of the `BinaryTree` class
