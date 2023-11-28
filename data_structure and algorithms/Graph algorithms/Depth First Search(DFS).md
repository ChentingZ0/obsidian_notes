Pre-order traversal of a graph
https://www.youtube.com/watch?v=PMMc4VsIacU&ab_channel=Reducible
Think of yourself as a bold and adventurous explorer where every time you see a new vertex, you will continue to explore new vertices until you hit a dead end in which case you retrace your steps and continue exploration.
For most time, O(n)
#### DFS Code Implementation 1(Recursive)
Cleaner and easier to read
```python
# G -> graph, v -> vertex
marked = [False] * G.size()
def dfs(G,v):
	visit(v)
	marked[v] = True
	for w in G.neighbors(v):
		if not marked[w]:
			dfs(G, w)
```
It's a very smart way to code. Recursively.

#### DFS Code Implementation 2(Iterative)
use the **stack** data structure
More generalizable!!!
```python
marked = [False] * G.size()
def dfs_iter(G,v):
	stack = [v]
	while len(stack) > 0:
		v = stack.pop()
		if not marked[v]:
			visit(v)
			marked[v] = True
			for w in G.neighbors(v):
				if not marked[w]:
					stack.append(w)
```

Both run in O(V+E)

To make it a post order implementation, all we have to do is instead of visiting a vertex as soon as we encounter a new vertex, we will now visit a vertex only after all its neighbors have been visited.
Only by moving the call to the visit function to the very end of the DFS post order function.
```python
# G -> graph, v -> vertex
marked = [False] * G.size()
def dfs(G,v):
	marked[v] = True
	for w in G.neighbors(v):
		if not marked[w]:
			dfs(G, w)
	visit(v)
```
Use HashSet to detect a duplicate nodes/cycle
#### Time complexity analysis
Consider a directed graph $G =(V,E)$ with $V = {v1, ... vn}$
Let $n = |V|$ and $m = |E|$
1. At the beginning, we mark all nodes as unvisted
- Time $O(n)$
2. How many times is each vertex added to the stack?
- At most once for each in-edge. Time for while loop $O(m)$
Total: $O(m+n)$

#### Problems
- Number of Islands
- Surrounded Regions
- Graph Valid Tree