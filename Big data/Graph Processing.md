### Graph partition
Graph partition will be a problem
Partition large scale graphs and distribute to hosts

1. Edge-Cut Graph Partitioning
Divide vertices of a graph into disjoint clusters
![[Pasted image 20230929132515.png]]
2. Vertex-Cut Graph Partitioning
Divide edges of a graph into disjoint clusters
![[Pasted image 20230929132523.png]]
duplicate the node into 3 copys


### PageRank 
PageRank (PR) is an algorithm used by Google Search to rank websites in their search engine results.
![[Pasted image 20230929142949.png]]
PageRank works by counting the number and quality of links to a page to determine a rough estimate of how important the website is.
### MapReduce
Problems: Mapreduce not directly support iterative algorithms

### Pregel
Large-scale **graph-parallel** processing platform developed at Google
inspired by bulk synchronous parallel(BSP) model
Message Passing Model
*Execution Model*: 
- Applications run in sequence of iterations, called supersteps
- A vertex in superstep S can: 
	• reads messages sent to it in superstep S-1. 
	• sends messages to other vertices: receiving at superstep S+1. 
	• modifies its state.
Vertices communicate directly with one another by sending messages.

Problems: has high delay, need to process all messages to go to the next iteration

### GraphLab
GraphLab allows asynchoronous iterative computation
Vertex scope of vertex v: the data stored in v, and in all adjacent vertices and edges.
A vertex can read and modify any of the data in its scope (shared memory).


**Gather-Apply-Scatter(GAS)**
**Gather**: accumulate information from neighborhood.
**Apply**: apply the accumulated value to center vertex.
**Scatter**: update adjacent edges and vertices.
PageRank(GraphLab - GAS)

```scala
PowerGraph_PageRank(i): 
	Gather(j -> i):
		return wji * R[j] 
	sum(a, b): 
		return a + b 
	// total: Gather and sum 
	Apply(i, total): 
		R[i] = total 
		
	Scatter(i -> j): 
		if R[i] changed then activate(j)
```

Think like a table:
Unifies data-parallel and graph-parallel systems.
### GraphX
only on scala, have no python API
GraphX is the library to perform graph-parallel processing in Spark
![[Pasted image 20230929144427.png]]

Pseudo-Code for Pregel, GraphLab, PowerGraph
*Review question:*
- Assume we have a graph and each vertex in the graph stores an integer value. Write three pseudo-codes, in Pregel, GraphLab, and PowerGraph to find the minimum value in the graph
1. *Pregel Pseudo-Code:*
```scala
i_val := val
for each message m:
	if m < val: then val := m

if i_val == val then
	vote_to_halt
else
	for each neighbor v:
		send_message(v, val)

```

2. *GraphLab Pseudo-Code*:
```scala
GraphLab_MinimumValue(i)
	// Initialize variables
	min_val = val;

	// Iterate over incoming neighbors
	foreach(j in in_neighbors(i))
		// Compute minimum value among neighbors
		if (R[j] < min_val)
			min_val = R[j];
	// Update the minimum value
	R[i] = min_val;
	
	// Trigger neighbors to run again
	foreach(j in out_neighbors(i))
		signal vertex-program on j;
```

3. *PowerGraph Pseudo-Code*
```scala
PowerGraph_MinimumValue(i)
	// Initialize variables
	min_val = val;

	// Gather phase: Compute minimum value from incoming neighbors
	Gather(j -> i)
		return (R[j] < min_val) ? R[j] : min_val;

	// Apply phase: Update the minimum value
	Apply(i)
		if (val < min_val)
		{
			min_val = val;
			R[i] = min_val;
		}
	// Check for convergence and vote to halt if necessary
	if (val == min_val)
		vote_to_halt
	else
	// Scatter: Signal neighbors to re-run their computations
		Scatter(i -> j)
```