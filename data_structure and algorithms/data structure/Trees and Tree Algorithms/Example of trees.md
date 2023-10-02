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