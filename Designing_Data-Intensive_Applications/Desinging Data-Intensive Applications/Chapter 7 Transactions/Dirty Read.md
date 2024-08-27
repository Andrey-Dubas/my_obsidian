Imagine a transaction has written some data to the database, but the transaction has not yet committed of aborted. Can another transaction see that uncommitted data? If yes, that is called ==dirty read==.

![[Dirty Read 2024-07-16 12.45.02.excalidraw]]
==No dirty reads user 2 sees the new value for x only after user 1's transaction has committed==
