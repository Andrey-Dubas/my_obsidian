The most traightforward approach for latch acquisition is to grab all the [[Latches]] on the way from the root to the target leaf. This creates concurrency bottleneck and should be avoided. The latch should be locked for minimal time. One of the optimisations used to achieve that called  [[Latch Crabbing]]  (Or [[Latch Coupling]]).
[[Latch Crabbing]] is rather a simple method that allow to minimize time holding latches. For reading we can release a latch for node as soon as we get to the child node and acquired its [[Latches]].
During insert, the latch could be released if it is guaranteed that there is no structural changes up to current node. In other words, ==a latch could be released if a child node is NOT full==.
Similarly during deletes.

Here is a list of operations during insert:
- The write [[Latches]] is acquired on the root node.
- Find a child node, if it is not full - acquire a write latch, release a root.
- and so on...
