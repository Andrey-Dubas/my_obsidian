holds a history of operations (log entries) applied to cached pages but not yet synchronized with persistent  storage to guarantee  they won't be lost in case of crash. Log entries can also be used to undo changes done by aborted transactions.
Example : [[write-ahead log (WAL)]]
