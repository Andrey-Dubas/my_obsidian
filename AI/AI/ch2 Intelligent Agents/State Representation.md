
Here from less complex to more:

#### Atomic Representation
**Atomic representation** - each state on the world indivisible - meaning it has no internal structure. e.g. consider finding a route thru a set of cities. Each city is a black box, so we are switching from one state to another.
The standard algorithms underlyiing seach and game-playing, [[Hidden Markov Models]] and [[Markov Decision Processes]] all work with atomic representation.
#### Factored Representation
A **factored representation** splits each state into a fixed state of variables and attributes, each of which can have a value. e.g. in self-driving car, a state could be Our GPS, gas in a tank, radio station, etc.
Many important areas in AI based on **factored representation** - [[Constrain Satisfaction Algorithms]], [[Propositional Logic]], planning, [[Bayesian Network]].
#### Structured Representation
Sometimes we need to express relationship between objects in a world. e.g. a camera sees a cow in a truck. It is unlikely there is a values in **factored representation**  of a tuck as TruckAheadBackingIntoDairyDrivewayBlockedByLooseCow with boolean value. Instead, we might use **structured representation** in which objects such as cow is blocking a truck's path. **Structured representation** underlie relational databases, [[First-Order Logic]], [[First-Order Probability Model]], Natural Language Understanding.

To gain the benefits of expressive representations while avoiding their drawbacks, intelligent system for the real world may need to operate at all representations.

**Localist representation** - one-to-one mapping of a concept and a memory in a computer.
**distributed representation** - ...
**Distributed representation** - are more robust against noise and information loss (???).
**With distributed representation, you can think of every concept as representing am point in multidimentional space, and if you garble a few bits you move to a nearby point in that space, which will have a similar meaning**.