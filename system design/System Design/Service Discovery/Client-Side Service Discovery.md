When using Client-Side Discovery, **the Service Consumer is responsible for determining the network locations of available service instances and load balancing requests between them.** The client queries the Service Register. Then the client uses a load-balancing algorithm to choose one of the available service instances and performs a request.

The following diagram shows the pattern just described:
[![Service Discovery Client Side](https://www.baeldung.com/wp-content/uploads/sites/4/2022/01/Service-Discovery-Client-Side.png)](https://www.baeldung.com/wp-content/uploads/sites/4/2022/01/Service-Discovery-Client-Side.png)
We can also point out that the Service Consumer and the Service Registry are quite coupled. This means that Client-Side Discovery logic must be implemented for each programming language and framework used by the Service Consumers.

![](https://microservices.io/i/servicediscovery/client-side-discovery.jpg)