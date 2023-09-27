### Bellman-Ford Algorithm
**Single source shortest path:**
shortest path algorithm that determines the shortest path between a given source vertex and every other vertex in a graph.

It can handle negative cost

Initialization: set all to infinity
iterate:
(u,v) where u means source node, v means target node,  c(u,v) means the cost/weight of the edge (can be negative)
"Relaxation" procedure:
```
if f(d[u] + c(u,v) < d[v]):
	d[v] = d[u] + c(u,v)
until it doesn't change
```

Time complexity: 
minimum: $O(n^2)$, maximum: $O(n^3)$(if the graph is complete graph)

### Dijkstra's Shortest path 
(Similar to Bellman-Ford Algorithm)
Single Source Shortest Path
Time complexity: $O(Elog(V))$
Data Structure: Minimum Heap(priority queue), HashSet
 
#### Problems
- [Network Delay Time](https://www.youtube.com/watch?v=EaphyqKU4PQ&ab_channel=NeetCode)
- Cheapest Flights Within K Stops




