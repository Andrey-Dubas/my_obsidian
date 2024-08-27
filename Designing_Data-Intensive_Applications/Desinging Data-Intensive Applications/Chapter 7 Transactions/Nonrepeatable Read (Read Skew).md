![[Nonrepeatable Read (Read Skew) 2024-07-17 21.43.00.excalidraw]]

On the pic "TRANSFER" an actor moves 100$ from account 1 to account 2.
Alice requests balance of account 1 during transaction (receives old value) and from account 2 after committed transfer transaction (receives new value).

Read Skew is an example of nonrepeatable read
