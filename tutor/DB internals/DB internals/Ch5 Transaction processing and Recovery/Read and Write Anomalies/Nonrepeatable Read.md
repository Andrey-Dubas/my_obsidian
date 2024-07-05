#fuzzy_read #read_anomaly 
Fuzzy Read a situation in which a row gets read twice with different results.

Transaction 1 reads - Transaction 2 modifies - Transaction 1 reads
Transaction read operations receive different result.
Both transactions are not committed.