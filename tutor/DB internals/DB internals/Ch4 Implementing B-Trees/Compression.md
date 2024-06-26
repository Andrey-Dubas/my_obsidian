compression is always a tradeoff between size of DB and CPU utilisation.
Compression can be done on different granularity level.
We could compress the whole index file, but then we need to decompress on access and decompress/compress on modification, that is impractical.
We can compress data page-wise. A compressed page can take less space than page.
![[Compression 2024-06-25 15.10.31.excalidraw]]
However, a compressed page  in this  case can only occupy a fraction of a disk block and, since transfers are usually done in units of disk blocks, it might necessary to page in extra bytes.
On picture you can see compressed page *a* taking less space than the disk block. When we load this page, we also page in additional bytes that belong to the other page.

Another approach is to compress data only (row-wise or column-wise). In this case page management and compression are decoupled.