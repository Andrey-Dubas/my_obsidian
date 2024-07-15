In practice, isolation is not that simple. Serialisable isolation has its performance penalty, and many DBs don't pay this price.

A popular comment on revelations of such problems is "Use an ACID database if you are handling financial data!" - but that misses the point.
\
[[Read Committed]] is the most basic level of isolation. It makes 2 guarantees:
 - When reading from DB, you will only see data that has been committed (no dirty reads)
 - When writing to the database, you will only overwrite data that has been committed.

[[No Dirty Reads]]

Imagine transactions has written data, but the transaction is not yet committed. Can another transaction read uncommitted data? If yes, it is called [[Dirty Read]].