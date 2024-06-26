

![[Sliding window algorithm 2024-06-25 12.19.02.excalidraw]]

Let's consider the following case:
rate-limiting just started to work, in 1 second it consumed 2 requests. During next 0.5 seconds it consumed 3 more requests.
So the formula used to calculate amount of requests for sliding window:
amount = 0.5 * (amount of requests during first minute) + (amount of requests during second minute) = 0.5 * 2 + 3 = 4

On 1.7 seconds the formula would be
amount = 0.3 * (amount of requests during first minute) + (amount of requests during second minute)