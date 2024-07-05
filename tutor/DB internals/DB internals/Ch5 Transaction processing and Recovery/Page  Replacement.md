#eviction_policy #page_perlacement_policy 
The most naive page-replacement strategy is FIFO.
Whenever the page is full, it takes the element from the head of the queue to find the page thast was paged in a fartherst point in time. Since it does not account for subsequent page access, only for page-in events, this proves to be impractical.
The natural extension of FIFO algo is [[LRU]]. It maintain sa queue of eviction candidates in insertion order, but allows you to place a page back to hte tail of the queue on repeated access.
[[CLOCK]] algorithm variants are often used as compact, cache-friendly, and concurrent alternatives to [[LRU]]. [[CLOCK]]-sweep holds references to pages and associated access bit in a circular buffer. Every time the page accessed (==referenced?== yes) its access bit is set to 1. The algo works by going around the circular buffer, checking access bits:
 - if the access bit is 1 and the page is unreferenced, it is set to 0, and the next page is inspected.
 - if the access page is already 0, the page becomes a *candidate* and is scheduled for eviction.
 - if the page is currently referenced, its access bit remains unchanged.
 Hand pointer  and  contents can be modified using compare and swap operations.