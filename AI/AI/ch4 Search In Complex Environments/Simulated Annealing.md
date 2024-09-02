Sometimes we need to go up the hill to go over a local maxima (ridge) to get to global minimum.
So we might accept a state with higher **objection function** with some probability.
Over time we "lower" that probability since we assume we passed all local minimums.
We accept a concept of temperature that affects this probability.
The algo:
- randomly choose the next state among adjacent states
- if the  next state have higher objection function - switch to next state
- otherwise calculate the probability of switching
$$
P = e^{\delta(E)/T}
$$
The T is a value of the function that decreases over time, therefore, the probability is getting lower.