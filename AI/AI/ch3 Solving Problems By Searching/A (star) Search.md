The algo is [[Best-First Search]] variation that chooses a node from priority queue (Therefore, we have [[Depth-First Search]]) by its priority:
$$
f(n) = g(n) + h(n) 
$$
Where g(n) is a path cost,
h(n) - heuristic function.
f(n) is therefore the estimated cost of the best path that goes thru n edge.
A* is complete, Whether A* is cost-optimal depends on certain properties of the heuristic. The key property is **admissibility** (приемлемость, допустимость).
#### Admissible heuristic
[[Admissible heuristic]] is the one that never overestimates the cost to reach a goal. Hence **admissible** heuristic is optimistic.
A* is cost-optimal, and we can show it by contradiction.
Suppose the optimal path cost is C*, but the algo returns C > C*.Then there is a optimal node n that is unexpanded. Then using notation g*(n) to mean the cost of optimal path from start to n and h*(n).

f(n) > C* (otherwise n would be expanded)
f(n) = g(n) + h(n)  (definition)
f(n) = g*(n) + h(n) (because n is on optimal path)
f(n) <= g*(n) + h*(n) (because of admissibility)
C <= C* - contradiction!

The heuristic is also **admissible** if its **consistent**. It is slightly stronger property.
Heuristic is **consistent** if
h(n) <= c(n, a, n') + h'(n)
![[A (star) Search 2024-08-28 13.56.10.excalidraw]]

With **consistent heuristic** the first solution the algo finds is optimal. Also, with consistent heuristic, a frontier will be monotonically increased.
A* is efficient because it **prunes** away search tree nodes that are not necessary for finding the optimal solution.

(???) Satisfying search
We can explore less nodes using inadmissible, but potentially more accurate heuristic. The solution we find might be suboptimal (**satisfying**).
We can apply this idea and make **weighted A* search** algorithm.
$$
f(n) = g(n) + h(n) * W
$$
where W is weight.

Weighted A* search can be seen as generalization of others algorithm

W = 0 -> f(n) = g(n) - [[Uniform-Cost Search]] or [[Dijkstra's Algorithm]]
W = 1 - A* search
W = infinite -> f(n) = h(n) - [[Greedy Best-First Search]]

() Memory-Bounded Search
**Beam search** keeps only k nodes of frontier that are with better (smaller) cost score.