Node size and tree fanout values are fixed and do not change dynamically.
The [[B-tree]] algorithm specifies that every node keeps a specific number of items. Since some values have different sizes, we may end up in a situation where, the [[node]] is not is not yet full, but there is no more space on the fixed-size [[page]].
Instead of allowing arbitrary pages, nodes are allowed to grow 4K increments, so we allocate a 4K extension page and link it from the original one. These linked page extensions are called [[overflow page]].

If SQL Server must allocate row-overflow pages, it adds a 24-byte pointer per row on the in-row page, pointing to the variable-length column's location on the row-overflow page, creating a link from in-row to row-overflow pages.

When the first overflow psage allocated, its page ID is stores in the header of the primary page. If a single overflow page is not enough, multiple overflow are linked together by storing the next overflow page ID in the previous one's header.