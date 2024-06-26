[[transaction]] is a set of write/read operation executed against the DB.
[[schedule]] is a list of operations required to execute a set of transactions from data-base-system perspective.
A schedule is ==complete== if it contains all operations of the set of transactions.

==correct== schedule is an equivalent to the original list of operations, but their parts can be executed in parallel of gets reordered.

a schedule is ==serial== if all the transactions in it are executed completely independently and without interleaving.
A schedule is [[serializable]] if it is ==a equivalent to some complete serial== schedule over the same set of transactions. In other word, it produces the same result as if executed a set of transaction one after another.
