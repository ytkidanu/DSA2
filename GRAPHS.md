# Graphs
### Intuitively understand the definitions of 

Big oh
- Less than or equal

Big theta, 
- equal

Big omega
- Greater than or equal

little o
- Strictly less than
little omega

Strictly larger
 
***be sure to know how they relate to evaluating the running time of algorithms
 Be able to demonstrate asymptotic bounds of functions***
 ---
 
### Understand the definition of a graph and definitions of various properties of graphs including:

G( V, E) - two sets of nodes and edges 
- v = integer E=unordered pairs, tuples

_Directed Graph_
- Edges are directed. 
- Edges only move in one direction, 
	- you can go from one to 2, but not 2 to one. If you want to do this then you need two directed edges connecting them.
- Sometimes we do allow an edge to connect to itself
- N * n-1 is maximum # of edges

_Undirected Graph_
- N * n-½ of edges
- Can go any direction on a edge, it is not directed

_Weighted Graph_
- Weight is information that is in addition to vertices and edges.
- It is a positive value that is associated with an edge
  - Function that maps every edge to a positive integer
  - We usually don't allow < 1 weight
- Often interpreted as cost to go across an edge


_Node degree_ (including in-degree and out-degree)

  _Degree_
  	 - Number of “neighbors” of a node

  _Indegree_ ( only Digraph )
    - Number of incoming edges

  _Outdegree_ ( only Digraph )
 	 - Number of outgoing edges

_Complete graph_
- Directed graph in which every pair of distinct vertices is connected by a pair of unique edges
- Dense graph
- Relatively high number of edges compared to nodes
- Sparse graph
- Relatively few edges compared to nodes
- Minimum number of edges a graph can have : 0
<img width="577" alt="Screen Shot 2023-12-15 at 9 37 09 PM" src="https://github.com/ytkidanu/DSA2/assets/123510145/34fcfc76-687b-47a7-91f3-edc0b1691c0f">


