[[Evolutionary Algorithms]] inspired by nature. There is a population of individuals, in which the fittest individuals produce offspring (successor states) that populates the next generation, a process called **recombination**.
There are some variations of algorithms
- the size of population
- the mixing number p, which is the number of parents; p = 1 means we have **stochastic bean search**, usually it is p = 2, but could be more
- The **selection** process for selecting who will become parent for an offspring; one possibility is to choose from all population proportional to its objection function value; another possibility is to randomly select n individuals, and then select p most fittest ones.
- recombination process. One approach is randomly select **crossover point** to split each of the parent's string.
- the **mutation rate** - how often offsprings have random mutations to their representation.
- The **makeup** of the next generation. That can be just newly formed offsprings, of it could include some top-scoring individuals from previous generation (**elitism**). the practice of **culling**, in which there is a threshold, and individuals evaluated below are discarded.
#### History
The theory of evolution was developed by Darwin (1859): variations occur in reproduction and will be preserved in successive generations approximately in proportion to their effect on reproductive fitness.
Gregor Mendel (1866) worked on probabilistic laws governing these processes.
Watson and Crick (1953) identified the structure of the DNA molecule and its alphabet.
James Baldwin (1896) learning can effectively relax the fitness landscape, leading to an acceleration in the rate of evolution. There is **Baldwin effect** that is a consequence that things that are hard to learn end up in the genome, but things that are easy to learn need to reside in genome.