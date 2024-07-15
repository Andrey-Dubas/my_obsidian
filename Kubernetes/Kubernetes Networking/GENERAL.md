The Kubernetes networking model is based on a flat address space. All pods in a cluster can directly see one another. Each Pod has its own IP address. There is no need to configure NAT. Containers in the same pod share their pod's IP address and can communicate with one another through localhost. This model is pretty opinionated, but once set up, it makes life considerably easier for both developers and administrators.  A pod represents traditional pod and a container represents a traditional process.


The [[Classless Inter-Domain Routing (CIDR)]] notation is often used for this purpose because it is more concise, encodes mode info. ==F.e. 172.27.15.0/24 means that the first 24 bits (3 octets are used for routing).
