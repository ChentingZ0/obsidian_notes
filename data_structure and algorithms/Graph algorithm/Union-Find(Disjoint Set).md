Union-Find is a **data structure** that keeps track of elements which are split into one or more disjoint sets. It has two primary operations: 
**find** and **union**.

**find**: given an element, tell you what group(set) that element belongs to
**union**: merges two groups together

$O(nlog(n))$
DataStructure:
Forest of Trees

```python
# find the parent
function find(x):
	if Parent[x]!=x:
		return find(Parent[x])
	else: return x

# merge the set(add link)
function union(x,y):
	parent[find(y)] = find(x)
```

Example:
- Graph Valid Tree


- **Number of Connected components in Undirected Graph**
(premium question)
Question:
You have a graph of n nodes. You are given an integer n and array edges where edges$[i] = [a_{i}, b_{i}]$ indicates that there is an edge between $a_{i}$ and $b_{i}$ in the graph. Return the number of connected components in the graph.
![[Pasted image 20230930202618.png]]
Intuition: 
1. can build adjacency list and use BFS to traverse'
2. union-find, natural way to detect disjoint sets

Maintain two arrays:
One called the parent array(initially Par[0,1,2,3,4]). Node itself is the parent by default. (change when merged)

The second called the Rank array(initially Rank[1,1,1,1,1]), increment one if the parent has one more child, basically indicates the size of the forest.(merge small into the large one to minimize the height of the tree, compare the rank)

```python
class Solution:
	def countComponents(self, n: int, edges: List[List[int]]) -> int:
		parent = [i for i in range(n)]
		rank = [1] * n

		def find(n1):
			res = n1
			while res != parent[res]:
				parent[res] = parent[parent[res]]
				res = parent[res]
			return res

		def union(n1, n2):
			p1, p2 = find(n1), find(n2)
			if p1 == p2:
				return 0
			if rank[p2] > rank[p1]:
				parent[p1] = p2
				rank[p2] += rank[p1]
			else:
				parent[p2] = p1
				rank[p1] += rank[p2]
			return 1
		
		res = n # number of connected component
		for n1, n2 in edges:
			res -= union(n1, n2)
		return res
```