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
Large-scale graph-parallel processing platform developed at Google
inspired by bulk synchronous parallel(BSP) model
Problems: has high delay, need to process all messages to go to the next iteration

### GraphLab
GraphLab allows asynchoronous iterative computation
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

### GraphX
only on scala, have no python API
GraphX is the library to perform graph-parallel processing in Spark
![[Pasted image 20230929144427.png]]
