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


How to decompose digraph into scc:
- Call dfs sweep to find finishing times for each vertex
- Compute transpose of digraph ( transpose means same nodes, edges reversed)
- Call dfs sweep on transpose graph in the order of decreasing finishing times

Bipartite
- An undirected graph is bipartite if every node can be assigned to one of two groups such that every edge “crosses teams”, On ipad i depicted this with two different color teams. - - Teams of the same color can not be connected by an edge.
- It is a graph with no odd length cycles
- Can use bfs to check if there is an edge to nodes on the same level. If there is, than that's an odd length cycle and thus… not bipartite 
  - Keep track of depth

**Be able to reason about the tradeoffs between using an adjacency list representation of a graph vs. an adjacency matrix representation**

 ---

### Understand the following algorithms/traversals to the extent that you could step through them manually and reason about hypothetical changes to them:

5.1 Graph Traversals - BFS & DFS -Breadth First Search and Depth First Search

_Breadth-First Search (BFS)_
- Can check if every node is reachable from a node. Count how many are reached, compare to number of nodes
- Outputs the distance from S to each node in G
- theta(E + V) linear
- Starts with node s, visits all neighbors of s, then all neighbors of neighbors of s

It is going to use a queue ( a first in first out method. We’re gonna mark s as seen, then add s neighbors to a queue , then we are going to  take one of s neighbors( t), mark that as seen and add t neighbors to the end of the queue. 


 _Depth-First Search (DFS)_
 - Strategy in words: START AT A node and then find one of its neighbors, then find one of the neighbors of the neighbor of the start. Keep doing this until you get stuck at a dead end. Back track as little as possible, then continue to go from that point. Eventually you'll return to where you started.

- You start with node s, visit one neighbor of s, then all nodes reachable from that neighbor, then another neighbor of  s ….
- Straight down the line
- Can quickly tells us if our graph has a cycle
- Tells us paths to tables
- And can do topological sorting to graph 
- Can be done none-recursively
  - Same algo as bfs, but diff structure
  - For bfs, we want queue because we want to make sure we go level by level through graph
  - Dfs, we want to go down quickly, so just put in a stack instead
- Much more common to write this recursively 
- Back edges tell us there is a cycle
  - Hard for undetected because you can go back up, but this isn't a cycle

_Dijkstra’s Algorithm_
- Finds shortest path in entire graph
- greedy approach (don't need to know that yet)
  - greedy because it chooses the locally best solution

_Element of O(n2)_
- Trying to prove that left side grows as fat or slower than right function
- N log n is better than n2 it grows slower than n^2 (?)
- Find c that proves this is true
- He did this by eliminating n
- Show n^2 is not element big O(n)

--- 

### How to prove something belongs to an order class

<img width="516" alt="Screen Shot 2023-12-15 at 9 55 00 PM" src="https://github.com/ytkidanu/DSA2/assets/123510145/eb1ac9e1-b8d3-428e-842c-151deec27678">

#### _Proof by Induction_

**Inductive Hypothesis:**

- **Claim 1:** There exists a path of length 'd' from node 's' to node 'u'.
- **Claim 2:** This path represents the shortest path.

**Base Case:**
For the node 's' with a distance of 0, the base case holds true here.

**K:** Number of items in set 's'.

### Divide and Conquer Algorithms

#### Mergesort

- When N = 1, the list is already sorted.
- For 'n' greater than 1, solve recursively and combine together in sorted sublists.

#### Karatsuba

- It divides the problem into multiple sub-problems and applies recursion to simplify multiplication.

#### Closest Pair of Points

- Split the problem in half.
- Find the closest pairs on the left, on the right, and within the cross area, returning the shortest of the three.
- Divide at the median coordinate. If odd, they go on one side or the other.
- Reduce the search space to 2 * delta (delta is the minimum).
- Base case is not 1 because you need to find a pair.

#### Strassen’s Algorithm

- Utilizes 7 equations and 7 multiplications along with 18 additions.
- The number of subproblems is 7, which is smaller than 8.
- Strassen found a way to reduce it to 7 subproblems.
---
## Recurrence Relations in Divide and Conquer Algorithms

Provide a recurrence relation to express the running time of a divide and conquer algorithm Solve recurrence relations using the Master Theorem and the Tree method. (We will give you the cases and text of the Master Theorem, so you don’t need to memorize it.)

### Recurrence Equation:

Given:
- **Divide:** 0 comparisons
- **Conquer:** Recursive on 2 small problems of size n/2
- **Combine:** n comparisons

Therefore, the recurrence relation is: T(n) = 2T(n/2) + n

### Induction Approach:

**Goal:** Prove P(k) holds.
**Base Case:** P(1) holds.
**Inductive Hypothesis:** Holds for all P(x) less than x greater than x, whatever that means.

### Guess and Check:

- T(n) = O(g(n))
- Consider: g * n = c * g(n)

**Induction:**
Show T(1) < g(1) which is also true for x and x+1.

### Karatsuba Guess and Check:

Given: T(n) = 3T(n/2) + 8n

- T(n) <= c * n^1.6 = O(n^1.6)
- Base case: T(1) = 8 <= 3000

### General Recurrence: T(n) = aT(n/b) + f(n)

**Case 1:** If f(n) is in O(n^logb(a-ϵ)) where ϵ > 0, f(n) grows a little slower.
**Case 2:** If f(n) grows at exactly the same rate as n^logb(a).
**Case 3:** If f(n) grows more quickly than n^logb(a).

**Examples:**

- For T(n) = 2T(n/2) + n:
  - Delta = logb(a) = log22 = 1
  - Compare f(n) to n^delta = n^1 = n
  - As f(n) matches n^1, T(n) = n log n

- For T(n) = 4T(n/2) + 5n:
  - Delta = log24 = 2
  - f(n) = 5n is slower than delta, so f(n) = O(n^2-1)
  - Case 1: Polynomial n to some constant (n^c)
  - Exponential is a constant to the power of n (c^n) - grows much more quickly.
