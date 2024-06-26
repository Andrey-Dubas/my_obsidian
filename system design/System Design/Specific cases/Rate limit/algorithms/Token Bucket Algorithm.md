Processes requests at dynamic rate (unlike [[Leaking Bucket]] algo).

We have a token bucket, or a container, that has predefined Bucket capacity.
We add tokens to a bucket at periodic time.
When a request come, it consumes a request.

The algorithm has 2 params:
bucket size
Refill rate


Deal with traffic burst better, since it can use all collected token once, while [[Leaking Bucket]]
only keeps a request in a queue
Pros:
- memory efficient
- allows bursts of traffic for short periods

Cons:
- which params to use 