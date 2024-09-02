
[[Admissible heuristic]] is the one that never overestimates the cost to reach a goal. Hence **admissible** heuristic is optimistic.
A* is cost-optimal, and we can show it by contradiction.
Suppose the optimal path cost is C*, but the algo returns C > C*.Then there is a optimal node n that is unexpanded. Then using notation g*(n) to mean the cost of optimal path from start to n and h*(n).

f(n) > C* (otherwise n would be expanded)
f(n) = g(n) + h(n)  (definition)
f(n) = g*(n) + h(n) (because n is on optimal path)
f(n) <= g*(n) + h*(n) (because of admissibility)
C <= C* - contradiction!