Occurs when each individual transaction respects the required invariants, but their combination does not satisfy these invariants.
We have 2 Transactions, T1, T2. 2 Accounts A1 A2
A1 = 100, A2 = 150.
The account values is allowed to be negative, as long as sum is positive: A1 + A2 >= 0.
Both transactions withdraw 200. After the commit the sum is negative.