[[Breadth-First Search]] always finds a solution with a minimal number of actions, because when it is generating nodes at depth d, it has already  generated all the nodes at depth d-1.
In terms of time and space, imagine searching a uniform tree where every node has b successors. The root generates frontier of b nodes, next level - b^2, b^3....
1 + b + b^2 + .... + b^d = O(b^d)
All nodes remain in memory