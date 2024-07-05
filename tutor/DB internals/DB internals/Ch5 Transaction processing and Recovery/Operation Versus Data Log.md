Some databases, e.g., [[System R]] use ==shadow paging==: a [[Copy On Write (COW)]] technique ensuring ==data durability== and ==transaction atomicity==. New contents are placed in [[shadow page]] and made visible with a pointer flip (where it is stored? [[page header]]?), from the old page to the one holding updated contents.
When a new content ready to become durable, all pages that refer to the current pages have to be updated.
[[write-ahead log (WAL)]] is more popular approach.
Any state change can be represented by ==before-image==, ==after-image== or by corresponding redo and undo operations. 
We can use [[Physical Log]] of [[Logical Log]]  to move records or pages from one state to another, both backward and forward. It is important to track exact state of the pages that physical and logical log records ca be applied to.
In practice, many DBs use a combination of 2 approaches, using [[Logical Log]]ging to perform undo (for concurrency and performance) and physical logging for redo (to improve recovery time).