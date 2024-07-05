Reference to [[ARIES]]
During a simple [[Checkpoint]], we must complete current transactions, flush the pages, and DO NOT start other transactions.
So the idea of Fuzzy [[Checkpoint]] is that we shouldn't stop database activity during checkpointing.
We store all dirty pages and its [[LSN (Log Serial Number)]] in [[Dirty pages table (DPT)]], 
![[Pasted image 20240625220152.png]]

we store all transactions and its statuses
![[Pasted image 20240625220222.png]]
and have modified [[write-ahead log (WAL)]] row content
![[Pasted image 20240625220332.png]]

And each page in dirty pages pool should contain Page [[LSN (Log Sequence Number)]]
![[Pasted image 20240625220546.png]]
The algorithm:
- write \<BEGIN CHPT\>
- flush it to the disk
- Flush [[Dirty pages table (DPT)]] and transaction table to the disk
- write \<END CKPT\> and flush to the disk
- 