This technique is used for autoincrementing indexes. In this case we append values only to the rightmost node, so it makes sense to cache it directly, given the ration of appends versus updates and deletes low.
[[postgreSQL]] calls this case *fastpath*,
[[SQLite]] calls it *quickbalancing*
