Tree is a particular type of graph
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


#### An Adjacency Matrix
![Adjacency Matrix](https://runestone.academy/ns/books/published/pythonds/_images/adjMat.png)
