[[Read Committed]] is the most basic level of isolation. It makes 2 guarantees:
 - When reading from DB, you will only see data that has been committed (no [[Dirty Read]])
 - When writing to the database, you will only overwrite data that has been committed (no [[Dirty Writes]])

This Isolation is usually achieved via locks: when a transaction wants to modify a record, it locks it until the transaction committed or aborted.

For dirty reads - acquire briefly a lock and after reading it - release.

That method is usually expensive, so usually for every object that is written database has 2 versions of an object: old and new, also acquiring a lock. While transaction is ongoing, read transaction simply read an old value.