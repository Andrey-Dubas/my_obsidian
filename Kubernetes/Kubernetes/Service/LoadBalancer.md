![[Pasted image 20240621145100.png]]


Exposes service to cloud-native load-balancer.

Whenever we create loadBalancer, NodePort and clusterIP created automatically.
So it uses NATIVE to platform load-balancer implementation.


port:
 - protocol: TCP
 - port: 3200
 - targetPort:3000
 - nodePort:30010