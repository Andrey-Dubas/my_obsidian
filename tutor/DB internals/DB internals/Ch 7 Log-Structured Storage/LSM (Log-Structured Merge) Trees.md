Immutable LSM trees use append-only storage and merge reconciliation.
In-place update storage structures are optimized for reads.
Append-only structures optimized for writes - we do not need to search for record, we just update them.
One of the most popular immutable on-disk storage structure [[LSM (Log-Structured Merge) Trees]] uses buffering and append-only storage structures.

==The [[LSM (Log-Structured Merge) Trees]] is a variant of of a disk-resident structure similar to [[B-tree]], where nodes are fully occupied, optimised for sequential access==.

LSM tree writes immutable files and merge them over time.

LSM tree defers data writes and buffer changes in a memory-resident table. These changes are then propagated by writing their contents out to immutable disk files.

Reads and writes do not intersect by design, so data on disk can be read without segment locking, so concurrent access is simplified.

[[LSM (Log-Structured Merge) Trees]] hate to merge and rewrite files to make sure that smallest possible number of files is accessed during the read.

[[LSM (Log-Structured Merge) Trees]] consists of 2 parts: smaller memory resident and larger data-resident components. To write out immutable file contents on disk, it is necessary to **buffer** them in memory and sort their contents.

The memory-allocated part is called [[Memtable]], and it is mutable.
Disk-resident components are used only for reads.