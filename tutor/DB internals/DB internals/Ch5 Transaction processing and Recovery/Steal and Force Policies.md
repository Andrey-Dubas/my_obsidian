[[Steal Policy]] is policy that allows flushing dirty pages BEFORE transaction is committed.
[[No-Steal Policy]]  forbids flushing dirty pages before transaction commit.
[[Force policy]] is policy that requires all dirty pages to be flushed before commit
[[No-Force Policy]] allows a transaction to be committed even if pages are  not flushed.

F.e., [[No-Steal Policy]] allows implementing recovery method using only redo entries:
old copy is contained on a disk and modification is stored in the log.

With [[No-Force Policy]] we can buffer several several changes to pages by *deferring them*. Page contents have to pages, so this require a larger page cache.

[[Force policy]] doesn't need any additional work to reconstruct the results of committed transactions, since pages modified by these transactions are already flushed.
Drawback: transactions take longer to commit due to I/O.

==More generally, until the transaction commits, we need to have enough information to undo its results. If any pages touched by the transaction are flushed, we need to keep undo information in the log until it commits to be able to rollback. Otherwise, we need to keep redo records in the log until commits. In both cases, transaction cannot commit until either undo or redo records are written to the logfile.==
