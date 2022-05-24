# Graphs



A grpah is a non-linear data structure that can be looked at as a collection of `vertices` (or `nodes`) potentially connected by line segments named `edges`

1. Vertex -  a "node", is a data object that can have zero or more adjacent vertices
2. Edge - connection between two nodes
3. Neighbor -  adjacent nodes, are connected via an edge.
4. Degree -  number of edges connected to that vertex

![ Graphs](./assets/Graph.png)

## Directed vs Undirected

- Undirected Graph - is a graph where each edge is undirected or bi-directional. This means that the indirected graph does not move in any direction.

- Directed Graph - also called a Digraph is a graph where every edge is directed. Each node is directed to another node with a specific requirement of what node should be referenced next.

## Complete vs Connected vs Disconnected

- There are many different types of graphs. This depends on how connected the graphs are to other node/vertices.

### Complete Graphs

- A complete graph is when all nodes are connected to all other nodes.

### Connected

- A connected graph is a graph that has all of vertices/nodes have at least one edge.

### Disconnect

- A disconnected graph is a graph where some vertices may not have edges. Bascially, a node will have not lines connecting to it. 

## Acylic vs Cyclic

### Acylic Graph

- An acyclic graph is a directed graph without cyles. A cycle is when a nodes can be traversed through and potentially end up back at itself. 
- Also called a DAG. This can also be represented as what we know as a tree.

### Cyclic Graphs

- A graph that has cycles.
- cycles is a path of positive length that starts and ends at the same vertex. Think of a circle. 

## Graph Representation

### Adjacency Matrix

- AM is represented through a 2-dimensional array. If there are n vertices, then we are looking at an n x n Boolean matrix.
- a sparse grapgh is when there are very few connections, a dense has many connections points.


### Adjacency List

- An adjacency list is the most comon way to represent graphs.
- it's a collection of linked lists or arrays that lists all of the other vertices that are connected.
- There arrows below represent edges, letters are nodes/vertices.


## Weighted Graphs

- A weighted graph is a graph with numbers assigned to its edges. These numbers are called weights. 
- when representing a weighted graph in a matrix, you set the element in the 2D array to represent the actual weight between the two paths.
- within adjacency list, you must include both the weight and the name of the adjacent vertex.


## Traversals

### Breadth First

- you start at a specific vertex/node. This node must be specified when call the `BreadthFirst()` method.
- The breadth-first traversal of a graph is similar to that of a tree, except graphs can have cycles and cause infinite loops.
- Keep track of the vertices/nodes that have been visited.


### Depth First

- Use a stack for a depth first search.
  1. Push the root node into the stack
  2. Start a while loop while the stack is not empty
  3. Peek at the top node in the stack
  4. If top node has unvisited children, mark the top node as visited, and then push any unvisited children back into the stack
  5. If top nodes does not have any unvisited children, Pop that node off the stack.
  6. repeat until the stack is empty.

### Resources

[Graphs](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/graphs.html)  