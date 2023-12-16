Quiz 3: Greedy
Terminology: Optimization problems involve finding the best solution with constraints. Feasible solutions meet problem constraints. The objective function ranks feasible solutions. Optimal solutions are the highest-ranking feasible ones.
Greedy choice property: Greedy algorithms make locally optimal choices, aiming for a globally optimal solution. They build solutions by stages, choosing the best item at each stage.
Dijkstra's Shortest Path is a greedy algorithm, always selecting the node with the shortest path.
Coin changing uses a greedy algorithm, picking the largest coin denomination that doesn't exceed the remaining amount. But this fails when denominations don't divide each other well.
Interval Scheduling Problems use a greedy approach to select the maximum-size set of mutually compatible activities.
Prim's and Kruskal's algorithms for Minimum Spanning Trees are greedy. Prim's selects the minimum edge connected to the already seen nodes, while Kruskal's adds the lowest edge that doesn't create a cycle.
Huffman coding, a greedy approach, minimizes the number of bits required to send a message using a prefix-free code.
Exchange argument: Demonstrates that a greedy choice is part of an optimal solution, showing the new solution isn't worse after exchanging an item from an optimal solution with the greedy choice.

Quiz 4: Dynamic Programming
Dynamic Programming (DP) focuses on optimal substructure and overlapping subproblems. It solves smaller subproblems first. DP compares to Greedy approaches with shared local decisions but differs in optimality and subproblems.
Log Cutting Problem and Matrix Chain Multiplication use bottom-up DP solutions. The log cutting problem finds the best way to cut a log for maximum profit, while matrix chain multiplication minimizes scalar multiplications for matrix sequences.
Longest Common Subsequence (LCS) Problem finds the longest subsequence in two sequences. Seam Carving determines the minimum cost seam in an image.
DP allows recovery of values that led to the optimal solution from the table. It exhibits optimal substructure, where larger problems contain solutions to smaller ones.
