also known as ==commit log==.
It is am append-only auxiliary ==disk-resident== structure used for crash and transaction recovery.Until cached contents are *flushed* to a disk, the only disk-resident copy preserving the operation history is stored in the WAL.
Many databasese use WAL, e.g., [[postgreSQL]] and [[MySQL]].
In addition to recovery, WAL plays importent role in transaction processing.

![[Pasted image 20240625215236.png]]
In the pic, we store that data for [[Fuzzy Checkpoint]].