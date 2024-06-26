also known as ==commit log==.
It is am append-only auxiliary ==disk-resident== structure used for crash and transaction recovery.Until cached contents are *flushed* to a disk, the only disk-resident copy preserving the operation history is stored in the WAL.
Many databasese use WAL, e.g., [[postgreSQL]] and [[MySQL]].
In addition to recovery, WAL plays importent role in transaction processing.

![[Pasted image 20240625215236.png]]
In the pic, we store that data for [[Fuzzy Checkpoint]].

Besides individual operation records, the [[write-ahead log (WAL)]] holds records indicating transaction completion. A [[transaction]] can't be considered commited until the log is forced up to the [[LSN (Log Serial Number)]] of its commit record.
To make sure the system can continue functioning correctly after a crash during rollback or recovery, some systems use [[compensation log records (CLR)]] during undo and store them in the log (as done for [[Fuzzy Checkpoint]] ing)