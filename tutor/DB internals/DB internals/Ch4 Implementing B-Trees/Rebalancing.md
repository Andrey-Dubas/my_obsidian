It is better to rebalance children in between siblings.
It improves utilisation.
It makes a tree shallower.
+ merges and splits are quite costly.
[[SQLite]]  e.g., uses this technique:
distribute data between siblings, as siblings are full - split 2 nodes into 3 nodes and redistribute elements (each one is occupied by 2/3)