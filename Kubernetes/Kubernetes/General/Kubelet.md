[[Kubelet]] is an node agent that communicates with [[Kube API Server]] and 
[[Kubelet]] runs on every single node (workers and [[Control Plane]])
[[Kubelet]] performs the ffollowing tasks:
	 - watches changes on the node
	 - configures the container runtime to
		 - run containers
		 - ==creates namespaces (????)==
		 - pulls images

![[Screenshot from 2024-07-05 15-09-36.png]]


The detailed picture

![[Pasted image 20240705151120.png]]


This node component is responsible for joining the cluster