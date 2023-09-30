Union-Find is a **data structure** that keeps track of elements which are split into one or more disjoint sets. It has two primary operations: 
**find** and **union**.

**find**: given an element, tell you what group that element belongs to
**union**: merges two groups together


O(nlogn)
DataStructure:
Forest of Trees


```
function find(x):
	if Parent[x]!=x:
		return find(Parent[x])
	else: return x

function union(x,y):
	parent[find(y)] = find(x)
```

Example:
- Number of Islands
- Number of Connected components in Undirected Graph
- Graph Valid Tree]