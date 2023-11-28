### Bellman-Ford Algorithm
**Single source shortest path:**
shortest path algorithm that determines the shortest path between a given source vertex and every other vertex in a graph.

It can handle negative cost

Initialization: set all to infinity
iterate:
(u,v) where u means source node, v means target node,  c(u,v) means the cost/weight of the edge (can be negative)
"Relaxation" procedure:
```python
if f(d[u] + c(u,v) < d[v]):
	d[v] = d[u] + c(u,v)
until it doesn't change
```

Time complexity: 
minimum: $O(n^2)$, maximum: $O(n^3)$(if the graph is complete graph)
#### Problems:
- [Cheapest Flights Within K Stops](https://www.youtube.com/watch?v=5eIK3zUdYmE&ab_channel=NeetCode)
(cannot simply use Dijkstra's because of the condition at most K stops)



### Dijkstra's Shortest path 
Use modified **priority queues**:
- Store tuples of (v, d) consisting of a vertex v and a distance d
The priority queue finds the minimum based on the d-values
**Operations**:
- *Insert(v, d)*:  Insert v into the heap with key d
- *decreaseKey(v, d)*: Changes the key of v to d; the new d-value must be smaller than before
- *findMin()*: Returns the vertex of smallest key in the heap (but does not delete it)
- *deleteMin()*: Deletes and returns the vertex with smallest key in the heap

**Pseudo code**:
```python
Q = an empty priority queue
for all v in V:
	Q.insert(v, +inf)
Let D be a dictionary and set D[v] = +inf for all v in V
Q.decreaseKey(s, 0)
D[s] = 0
While Q.isEmpty() == False:
	(u,d) = Q.deleteMin()
	for all v in neighbors(u):
		dv' = d + w_{uv}
		if dv'< D[v]:
			Q.decreaseKey(v, dv')
			D[v] = dv'
```
Note: D[v] stores the length of the shortest path from s to v

#### Time Complexity Analysis
The running time of Dijkstra’s algorithm is $O(m+nlogn)$
• Using Fibonacci heaps, we can perform decreaseKey() in time $O(1)$ and deleteMin() in time $O(logn)$
So: ->
 • Fibonacci heaps are a very efficient implementation of priority queues 
 • Each edge is traversed once and triggers at most one decreaseKey() operation 
	 • Takes total time $O(m)$
 • Each vertex will be extracted exactly once from the priority queue using deleteMin() 
	 • Takes total time $O(nlogn)$
 


(Similar to Bellman-Ford Algorithm)
Single Source Shortest Path
Time complexity: $O(Elog(V))$
Data Structure: Minimum Heap(priority queue), HashSet
 
#### Problems
- [Network Delay Time](https://www.youtube.com/watch?v=EaphyqKU4PQ&ab_channel=NeetCode)





