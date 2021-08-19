# Graphs
### Definitions : 
* Graph: a non-linear data structure; a collection of vertices ( nodes) connected potentially by edges (line segments)
* Vertex: a node/data object, it can zero or more adjacent vertices.
* Edge:  a connection between two nodes.
* Neighbor: adjacent nodes of a vertice
* Degree: number of edges connected to a vertex.


### Graphs Types:

* Undirected Graphs :

 Each edge is undirected or bi-directional 
 Example:


        Vertices/Nodes = {a,b,c,d,e,f}
        Edges = {(a,c),(a,d),(b,c),(b,f),(c,e),(d,e),(e,f)}
 
* Directed Graphs (Digraph):

every edge is directed
Digraph has arrows pointing to specific nodes.


### Complete vs Connected vs Disconnected :
* A complete graph is when all nodes are connected to all other nodes.
* A connected graph is a graph that has all vertices/nodes that have at least one edge.
* A disconnected graph is a graph where some vertices may not have edges.


### Graph Representation : 
* Adjacency Matrix
* Adjacency List
 
### Weighted Graphs :
a graph with numbers(weights) assigned to its edges.

### Graphs Traversals
* Breadth First :
Algorithm:
1. Enqueue the declared start node into the Queue.
2. Create a loop that will run while the node still has nodes present.
3. Dequeue the first node from the queue
4. if the Dequeue‘d node has unvisited child nodes, add the unvisited children to visited set and insert them into the queue.

* Depth First
Algorithm:
1. Push the root node into the stack
2. Start a while loop while the stack is not empty
3. Peek at the top node in the stack
4. If the top node has unvisited children, mark the top node as visited, and then Push any unvisited children back into the stack.
5. If the top node does not have any unvisited children, Pop that node off the stack
6. repeat until the stack is empty.

### Real World Uses of Graphs :
* GPS and Mapping
* Driving Directions
* Social Networks
* Airline Traffic
* Netflix uses graphs for suggestions of products