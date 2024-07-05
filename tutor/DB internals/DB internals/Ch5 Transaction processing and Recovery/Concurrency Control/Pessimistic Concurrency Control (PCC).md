easiest lock-free version timestamps all the transactions, and a transaction is allowed to modify value if any transaction with later timestamp was already committed.
Read operations that attempt to read a value with a timestamp lower that max_write_timestamp cause the transaction to be aborted, since there is already a new value.

[[Lock-Based Concurrency Control]]
One of the most widespread techniques is [[Two-Phase Locking (2PL)]] :
1) The *growing phase* (also called expanding phase) during which all locks required by the transaction are acquired and no lokcs are released.
2) The shrinking phase, during which all locks acquiter during the growing phase are released.


### deadlocks
The simplest way to  handle deadlocks is to introduce timeouts and abort long-running transactions under assumptions that they might be in deadlock.

Detecting deadlocks is generally done using [[Wait-for Graph]], which tracs relationships between the in-flight transactions and establish wait-for relationship between them