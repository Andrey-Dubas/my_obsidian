Let's take as an example a restaurant, which has a strange rule:
- each day only 1 meal is served.
- Tomorrow's meal is defined by a meal yesterday.

![[Pasted image 20240820181315.png]]
What is the probability of each meal?
Let's start from 1 meal and generate meals for next 10 days
B - burger
P - pizza
H - hot dog
B - P - H - B - H - B - P - H - H
4 - burger's day
2 - Pizza
4- hot-dog
4/10 - probability of burger day
4/10 - hot-dog
2/10 - pizza
Does it convergent to any specific value? Yes, if we repeat many times, we receive the following:
P(pizza) - 0.21245
P(burger) - 0.35191
P(hot-dog) - 0.41...
In fact, we pan calculate it!
We can convert the graph above by adjacency matrix,
    0.2   0.6   0.2
A =  0.3   0     0.7
    0.5   0     0.5

Let's denote it as **Transition Matrix**.
Let's choose initial position, expressed by a vector

$$
\Pi\ = [0\ \ 1\ \ 0]
$$


Let's Find next state by multiplying current state with transition matrix
$$
\Pi\0 \x\ A = \Pi\ 1 
$$
Calculation of the second day:
![[Pasted image 20240820183013.png]]

$$
\Pi\0 \x\ A = \Pi\ 1 
$$
This formula is very similar to aigenvector's one
$$
\Pi\ A = \lambda\\Pi\ 
$$
To be Markov's chain, elements should obey rules
1) elements of Pi should add up to 1 - since these are probabilities
2) 