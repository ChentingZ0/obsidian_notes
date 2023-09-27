Spanning tree is the sub graph of a graph
tree will not have a circle.
Minimum Spanning Tree is a tree with the minimum weight sum. 
连通无向图 $G = (V,E)$ 找到一个无环子集, 能够将所有的结点连接起来, 又具有最小的权重, 即$w(T) = \sum_{(u,v) in T} w(u,v)$最小. 我们称这样的问题为求图G的最小生成树问题. 

解决最小生成树问题的两种算法: Kruskal算法和Prim算法, 都属于贪心算法(greedy methods)
### Kruskal algorithm
Key principle: Always select a minimum cause edge but if it is forming a cycle don't include that edge 
Data structure: MinHeap
Time complexity: $O(nlog(n))$

### Prim's Algorithm
Key principle: Always maintain a tree. 
select the minimum edge connected to the already picked nodes to form a tree.

##### Problems:
