Occurs when transaction both modifies record. T1 writes value V1 and commits, T2 writes V2 and commits. T1 is overwritten by T2 => V1 is lost

==(Q: Why it is anomaly?)==
Possible A: If operations were reordered.
