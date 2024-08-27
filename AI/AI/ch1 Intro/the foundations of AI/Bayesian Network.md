A Bayesian Network is a probabilistic graphical model that measures the conditional dependence structure of a set of randor variables based on the [[Bayes Theorem]]:
$$
P(A|B) = P(B/A) * P(A)/P(B)
$$
Pearl (1988) stated that [[Bayesian Network]]s are graphical models that contain information about causal probability relationships between variables and are often used to aid in **decision making**.
There are 2 components involved in learning [[Bayesian Network]]:
- structure learning, which involves discovering the DAG that best describes the causal relationships in the data
- parameter learning, which involves learning about the **conditional probability**.

The 2 most popular methods for determining the structure of the DAG are the DAG search algorithm and [[K2 Algorithm]].