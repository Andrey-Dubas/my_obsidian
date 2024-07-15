#read_anomaly 
Dirty Read is a situation in which a transaction can read uncommitted changes from other transaction. F.e. Transaction 1 writes result, transaction 2 read updated value, transaction 2 rolls back. Officially, write didn't exist, but transaction 2  read it.

- transaction 1 writes X = 2
- transaction 2 reads X (X=2)
- transaction 1 commits

Problem: transaction 2 can't read what transaction 1 wrote BEFORE transaction ends.