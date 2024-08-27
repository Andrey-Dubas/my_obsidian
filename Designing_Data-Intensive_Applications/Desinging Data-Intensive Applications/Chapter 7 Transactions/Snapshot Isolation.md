  If one looks at [[Read Committed]] isolation, one could be forgiven for thinking that it does everything that transaction need to do: it allows aborts (required for atomicity), it prevents reading the incomplete results of transaction and prevents concurrent writes.
[[Write Skew]] might happen

![[Snapshot Isolation 2024-07-16 12.05.51.excalidraw]]
This is an example of [[Write Skew]] anomaly

[[Snapshot Isolation]] is the most common solution to this problem. The idea is that  each transaction reads from ==consistent snapshot== of the database - that is, the transaction sees all the data that was committed in the database at the start of the transaction.

To implement [[Snapshot Isolation]], datababa must potentially keep several different committed versions of an object, because various in-progress transactions may need to see the state of the database at different points of time. Because it maintains several versions of an object side by side, the technique is known as [[Multi-Version Concurrency Control (MVCC)]].

The technique used in [[PostgreSQL]].

