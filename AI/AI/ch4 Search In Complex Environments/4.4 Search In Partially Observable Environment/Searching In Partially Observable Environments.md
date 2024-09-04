Many problems cannot be solved without sensing. e.g. 8-queen problem. But it is solvable given we observe just upper left corner.
For Partially observable problem, the problem specificaton will specify a PERCEPT(s) function that returns percept received by an agent in a given state. If sensing non-deterministic, PERCEPT returns a set of possible states.
Consider a vacuum cleaner problem, in which agent returns a state of current tile it is on. We can think of a **transition model** between belief states for partially observable problems as occuring in three stages.
- **Prediction stage** computes a belief state resulting from the action, RESULT(b, a), exacly what we did with sensorless problems. To emphasize that this is a prediction, we use notation
$$
b hat = RESULT(b, a)
$$
- The **possible percepts** stage computes the set of percepts that could be observed in the predicted belief state (letter o for observation)
$$
POSSIBLE-PERCEPTS(b hat) = {o: o = PERCEPT(s) and s E b hat}
$$
- The **update** stage computes, for each possible percept, the belief state that would result from the percept. The updated belief state b0 is the set of states in b{hat} that could have produced the percept:
$$
b0 = UPDATE(b hat, o) = {s: o = PERCEPT(s) and s E b hat}
$$

Long story short:
1) prediction stage: belief state from action, RESULT(b, a)
2) possible percepts stage computes the set of percepts that could be observed in b^
3) Update stage: computes the belief state from possible perceipts/