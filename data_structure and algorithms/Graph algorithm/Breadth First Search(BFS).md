level-order traversal of a graph
https://www.youtube.com/watch?v=xlVX7dXLS64&ab_channel=Reducible
visit all the neighboring vertices, then to the next level.

#### BFS Implementation
use the queue data structure
```python
# psudeo code
marked = [False] * G.size()
def bfs(G,v):
	queue = [v]
		while len(queue) > 0:
			v = queue.pop(0) 
			if not marked[v]:
				visit(v)
				marked[v] = True
				for w in G.neighbors(v):
					if not marked[w]:
						queue.append(w)
``` 

(Use **HashSet** to detect a duplicate nodes/cycle)
Python:
```python
# popleft would be BFS, popright would be DFS
q = collections.deque()
q.append(...)
... = q.popleft()
```
#### Problems
- [Shortest Path in Binary Matrix](https://leetcode.com/problems/shortest-path-in-binary-matrix/description/)
- Word Ladder
- Clone Graph

- [Number of Islands](https://www.youtube.com/watch?v=pV2kpPD66nE&ab_channel=NeetCode)**(famous interview question)