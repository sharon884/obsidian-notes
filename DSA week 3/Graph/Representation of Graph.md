
A [****Graph****](https://www.geeksforgeeks.org/dsa/introduction-to-graphs-data-structure-and-algorithm-tutorials/) is a non-linear data structure consisting of vertices and edges. The vertices are sometimes also referred to as nodes and the edges are lines or arcs that connect any two nodes in the graph. More formally a Graph is composed of a set of vertices(****V****) and a set of edges(****E****). The graph is denoted by ****G(V, E)****.

## Adjacency Matrix Representation

An adjacency matrix is a way of representing a graph as a boolean matrix of (0's and 1's).

Let's assume there are n vertices in the graph So, create a 2D matrix adjMat[n][n] having dimension n x n.

> - If there is an edge from vertex i to j, mark adjMat[i][j] as 1.
> - If there is no edge from vertex i to j, mark adjMat[i][j] as 0.



### Representation of Undirected Graph as Adjacency Matrix:

![1-](https://media.geeksforgeeks.org/wp-content/uploads/20251028181828547875/1-.webp)


- We use an adjacency matrix to represent connections between vertices.
- Initially, the entire matrix is filled with 0s, meaning no edges exist.
- There is an edge between vertex 0 and vertex 1,so we set mat[0][1] = 1 and mat[1][0] = 1.
- There is an edge between vertex 0 and vertex 2,so we set mat[0][2] = 1 and mat[2][0] = 1.
- There is an edge between vertex 1 and vertex 2,so we set mat[1][2] = 1 and mat[2][1] = 1.


### Representation of Directed Graph as Adjacency Matrix:

![file](https://media.geeksforgeeks.org/wp-content/uploads/20251028181904555921/file.webp)

- Initially, the entire matrix is filled with 0s, meaning no edges exist.
- Unlike an undirected graph, we do not set mat[destination][source] because the edge goes in only one direction.
- There is an edge between vertex 1 and vertex 0,so we set mat[1][0] = 1.
- There is an edge between vertex 2 and vertex 0,so we set mat[2][0] = 1.
- There is an edge between vertex 1 and vertex 2,so we set mat[1][2] = 1.