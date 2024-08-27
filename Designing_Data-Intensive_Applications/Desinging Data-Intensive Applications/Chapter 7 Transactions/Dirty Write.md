Imagine there are 2 transactions trying to modify the same record. Who would win?
Operation that happens later wins.

What happens if earlier transaction writes data that has not been committed yet and the latter transaction overwrites uncommitted data? It is called [[Dirty Write]].

![[Dirty Write 2024-07-17 21.07.35.excalidraw]]
f.e. in the picture both transactions modifies listing and invoices, but without [[Read Committed]] isolation Alice gets a product and Bob receives invoice for it.
