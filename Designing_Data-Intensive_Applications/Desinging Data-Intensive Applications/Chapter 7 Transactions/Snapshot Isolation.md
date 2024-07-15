
[[Snapshot Isolation]] is the most common solution to this problem. The idea is that  each transaction reads from consistent snapshot of the database - that is, the transaction sees all the data that was committed in the database at the start of the transaction.

To implement [[Snapshot Isolation]], datababa must potentially keep several different committed versions of an object, because various in-progress transactions may need to see the state of the database at different points of time. Because it maintains several versions of an object side by side, the technique is known as [[Multi-Version Concurrency Control (MVCC)]].

The technique used in [[PostgreSQL]].

