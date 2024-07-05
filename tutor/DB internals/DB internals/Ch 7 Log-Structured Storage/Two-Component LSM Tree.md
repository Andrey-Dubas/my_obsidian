We distinguish between 2- and multicomponent [[LSM (Log-Structured Merge) Trees]]. [[Two-Component LSM Tree]] has only one disk component, comprised of immutable ==segments==.
The disk component here is organized as a [[B-tree]], with 100% node occupancy.

![[Two-Component LSM Tree 2024-06-28 17.27.32.excalidraw]]
[[Two-Component LSM Tree]] before a flush. Flushing memory- and disk- resident segments are shown in gray

![[Two-Component LSM Tree 2024-06-28 17.33.41.excalidraw]]
[[Two-Component LSM Tree]] after flush. Merged contents are shown in gray. Boxes with dashed lines depict discarded on-disk segments.

==Even though [[Two-Component LSM Tree]] can be useful for maintaining index files, no implementation are known to the author as of time of writing==.
