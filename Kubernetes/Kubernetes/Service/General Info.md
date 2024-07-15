
Which Pods to forward the request to?
The Ports are identified via selector or labels

Services operate on layer 3 level (TCP/UDP)


==LoadBalancer Service is an extension of NodePort Service==
==NodePort Service is an extension of ClusterIP Service== 

NodePort Service NOT for external connection, but rather to test sertvice quickly.

The most common configuration


![[Pasted image 20240621151108.png]]