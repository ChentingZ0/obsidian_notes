Tree is a particular type of graph

![[Pasted image 20231128183651.png]]
Consider a directed graph $G =(V,E)$ with $V = {v1, ... vn}$
Let $n = |V|$ and $m = |E|$
### Components
##### Vertex
also called a "node". It can have a name, which we call the "key"

##### Edge
An edge connects two vertices to show the relationship between them. If the edges in a graph are all one-way, we say the graph is a **directed graph/ diagraph**. 

##### Weight
cost to go from one vertex to another.

##### Path
A sequence of vertices that are connected by edges.

##### Cycle
A directed graph with no cycles is called **directed acyclic graph(DAG)**
![graph](https://runestone.academy/ns/books/published/pythonds/_images/digraph.png)
$$
\begin{split}E = \left\{ \begin{array}{l}(v0,v1,5), (v1,v2,4), (v2,v3,9), (v3,v4,7), (v4,v0,1), \\
             (v0,v5,2),(v5,v4,8),(v3,v5,3),(v5,v2,1)
             \end{array} \right\}\end{split}
$$
$$
V = \left\{ V0,V1,V2,V3,V4,V5 \right\}
$$



#### Graph Abstract Data Type(ADT)
The graph abstract data type (ADT) is defined as follows:
- `Graph()` creates a new, empty graph.
- `addVertex(vert)` adds an instance of `Vertex` to the graph.
- `addEdge(fromVert, toVert)` Adds a new, directed edge to the graph that connects two vertices.
- `addEdge(fromVert, toVert, weight)` Adds a new, weighted, directed edge to the graph that connects two vertices.
- `getVertex(vertKey)` finds the vertex in the graph named `vertKey`.
- `getVertices()` returns the list of all vertices in the graph.
- `in` returns `True` for a statement of the form `vertex in graph`, if the given vertex is in the graph, `False` otherwise.



#### Representations of Graph
How to store Graphs
1. **Adjacency Matrix**
If there is an edge from vertex i to j, mark $adjMat[i][j] = 1$, otherwise mark $adjMat[i][j] = 0$
![undirected](https://media.geeksforgeeks.org/wp-content/uploads/20230727130331/Undirected_to_Adjacency_matrix.png)
![DAG](https://media.geeksforgeeks.org/wp-content/uploads/20230727130528/Directed_to_Adjacency_matrix.png)




2. **Adjacency List**
$adjList[0]$ will have all the nodes which are connected (neighbour) to vertex 0
$adjList[1]$ will have all the nodes which are connected (neighbour) to vertex 1 and so on.

The below undirected graph has 3 vertices. So, an array of list will be created of size 3, where each indices represent the vertices. Now, vertex 0 has two neighbours (i.e, 1 and 2). So, insert vertex 1 and 2 at indices 0 of array. Similarly, For vertex 1, it has two neighbour (i.e, 2 and 1) So, insert vertices 2 and 1 at indices 1 of array. Similarly, for vertex 2, insert its neighbours in array of list.
![adjacency list](https://media.geeksforgeeks.org/wp-content/uploads/20230727154843/Graph-Representation-of-Undirected-graph-to-Adjacency-List.png)

```java
class Graph{
    private int numVertices;
    private LinkedList<integer> adjLists[];
}
```

```python
graph = {'A': set(['B', 'C']),
         'B': set(['A', 'D', 'E']),
         'C': set(['A', 'F']),
         'D': set(['B']),
         'E': set(['B', 'F']),
         'F': set(['C', 'E'])}
```

```python
adj = [[] for _ in range(numCourses)]
```