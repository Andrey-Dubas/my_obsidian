![[Hill-Climbing Search 2024-08-28 15.56.16.excalidraw]]
It keeps track of current state and moves to the neighboring state with the highest value - in a direction of the **steepest ascent**.
[[Hill-Climbing Search]] is also sometimes called **greedy local search** as it moves to state with highest **objection function**.

**Local maxima** can stuck the algorithm.
**Ridge** results in a sequence of local maxima that is very difficult for greedy algorithm to navigate.
**Plateaus** is a flat area of the state-space landscape. It can be flat local maximum, from which no uphill exists, or a **shoulder**, from which progress is possible (see the graph). We can allow **sideways move** in the hope that the plateau is a shoulder.
#### Stochastic Hill Climbing
Chooses at random from uphill moves; the probability of selection can vary with the steepness of the uphill move. This usually converges more slowly, but in some landscapes provides better solution.

#### Random-Restart Hill Climbing
Conducts a series of hill-climbing searches from random initial states.