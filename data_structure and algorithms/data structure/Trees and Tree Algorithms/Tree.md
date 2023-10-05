## Example of trees
#### web page
an example of a web page written using HTML.
```html
<html xmlns="http://www.w3.org/1999/xhtml"
      xml:lang="en" lang="en">
<head>
    <meta http-equiv="Content-Type"
          content="text/html; charset=utf-8" />
    <title>simple</title>
</head>
<body>
<h1>A simple web page</h1>
<ul>
    <li>List item one</li>
    <li>List item two</li>
</ul>
<h2><a href="http://www.cs.luther.edu">Luther CS </a><h2>
</body>
</html>
```
![structure](https://runestone.academy/ns/books/published/pythonds/_images/htmltree.png)

#### List representation of tree structure
```python
myTree = ['a',   #root
      ['b',  #left subtree
       ['d', [], []],
       ['e', [], []] ],
      ['c',  #right subtree
       ['f', [], []],
       [] ]
     ]
```
Access subtrees of the list using list indexing
root -> 'a': myTree[0]
left subtree -> 'b': myTree[1]
right subtree -> 'c': myTree[2]

## Parse Tree
$(7+3)\times(5-2)$
![structure](https://runestone.academy/ns/books/published/pythonds/_images/meParse.png)
[explanation](https://runestone.academy/ns/books/published/pythonds/Trees/ParseTree.html)

```python
from pythonds.basic import Stack
from pythonds.trees import BinaryTree

def buildParseTree(fpexp):
    fplist = fpexp.split()
    pStack = Stack()
    eTree = BinaryTree('')
    pStack.push(eTree)
    currentTree = eTree

    for i in fplist:
        if i == '(':
            currentTree.insertLeft('')
            pStack.push(currentTree)
            currentTree = currentTree.getLeftChild()

        elif i in ['+', '-', '*', '/']:
            currentTree.setRootVal(i)
            currentTree.insertRight('')
            pStack.push(currentTree)
            currentTree = currentTree.getRightChild()

        elif i == ')':
            currentTree = pStack.pop()

        elif i not in ['+', '-', '*', '/', ')']:
            try:
                currentTree.setRootVal(int(i))
                parent = pStack.pop()
                currentTree = parent

            except ValueError:
                raise ValueError("token '{}' is not a valid integer".format(i))

    return eTree

pt = buildParseTree("( ( 10 + 5 ) * 3 )")
pt.postorder()  #defined and explained in the next section

```


## Nodes and references
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


## Tree Traversals
which order to visit all the nodes.
Three traversals: preorder, inorder, postorder

```python
# recursive way to write preorder
def preorder(tree):
	if tree:
		print(tree.getRootVal())
		preorder(tree.getLeftChild())
		preorder(tree.getRightChild())
```