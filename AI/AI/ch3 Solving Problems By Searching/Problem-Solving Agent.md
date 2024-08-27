When the correct action is not obvious, an [[Agent]] might need to _plan ahead_: to consider a sequence of actions that form a path to the goal state. Such agent is called [[Problem-Solving Agent]] and the computational process it  undertakes is **search**.
[[Problem-Solving Agent]] use **atomic** representation (see [[State Representation#Atomic Representation]]).
[[Problem-Solving Agent]] that use **factored** or **structured** representation caller **planning agent**.

Example:
An agent enjoying a vacation in Romania. The agent wants to take in the sights.....
**given** map if Romania - cities as vertice, distances as edges.
**Goal formulation**: the [[Agent]] adopts a **goal** of reaching Bucharest. Goals organize behavior by limiting the objectives and hence the actions to be considered.
**problem formulation**: the [[Agent]] devises a description of the states and actions necessary to reach the goal - an abstract model of the relevant part of the world. One good model is to consider actions of travelling from one city to another.
**Search**: Agent simulates sequence of actions to reach the goal. Such a sequence is called a **solution**.

It is important property that in a **fully observable**, **deterministic**, **known environment**, _the solution to any problem is a fixed sequence actions_. e.g. Drive to Sibiu, Fagaras, Bucharest.
If the model is correct, the agent can ignore percept, because the solution is guaranteed to the solution. Control theorist call it **open-loop** system: ignoring percepts breaks the loop between agent and environment.
In partially observable or nondetermenistic environment a solution would be a branching strategy that recommends different future actions depending on percepts.