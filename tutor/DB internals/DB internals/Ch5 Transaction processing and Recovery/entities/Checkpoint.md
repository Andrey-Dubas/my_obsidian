Idea: save the state the database periodically so that we do not need to always process the entire log during recovery
During a checkpoint:
 - stop accepting new transactions
 - wait until all current transactions complete
 - flush log to disk
 - flush all dirty pages to disk
 - write <CKPT> log record, flush log again
After that, we are ready to resume to transactions
During recovery, we execute commands from [[write-ahead log (WAL)]]  from the last <CKPT>. We even can truncate WAL.

