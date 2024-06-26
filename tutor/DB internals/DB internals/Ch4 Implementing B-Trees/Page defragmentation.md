#vacuum
The process that takes care of space reclamation and page rewrites is called *compaction, vacuum, maintenance*.
Unused in-memory pages become available and are returned to the page cache, IDs of the newly available on-disk pages are added to the **free page list (freelist)**. This info has to be persisted to survive crash.