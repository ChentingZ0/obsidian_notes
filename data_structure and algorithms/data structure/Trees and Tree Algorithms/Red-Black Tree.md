- A node is either red or black
- The root and leaves(NIL) are black
- If a node is red, then its children are black
- All paths from a node to its NIL descendants contain the same number of black nodes.

- Nodes require one storage bit to keep track of color
- The longest path(root to farthest NIL) is no more than twice the length of the shortest path(root to nearst NIL).
  Shortest path: all black nodes
  Longest path: alternating red and black nodes


**Operations**: 
Search
Insert: require rotation
Remove: require rotation
Time complexity of $O(log(n))$.
Space complexity: $O(n)$.

