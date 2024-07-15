The pod IP addresses are not visible externally.
Cloud provider balancers are not Kubernetes aware, so they can't direct traffic to a particular service directly to a node that runs a pod that can process the request.
Instead, ==the public load balancer directs traffic to any node in the cluster and kube-proxy on that node will redirect again to an appropriate pod==.