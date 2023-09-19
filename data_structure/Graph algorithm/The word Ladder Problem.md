Transform the word “FOOL” into the word “SAGE”. In a word ladder puzzle you must make the change occur gradually by changing one letter at a time. At each step you must transform one word into another word, you are not allowed to transform a word into a non-word.
```
FOOL
POOL
POLL
POLE
PALE
SALE
SAGE
```
We are interested in figuring out the smallest number of transformations needed to turn the starting word into the ending word.

Two steps:
- Represent the relationships between the words as a graph.
- Use the graph algorithm known as breadth first search to find an efficient path from the starting word to the ending word.

![graph](https://runestone.academy/ns/books/published/pythonds/_images/wordgraph.png)
