
**The alternate approach to Service Discovery is the Server-Side Discovery model, which uses an intermediary that acts as a [Load Balancer](https://www.baeldung.com/zuul-load-balancing).** The client makes a request to a service via a load balancer that acts as an orchestrator. The load balancer queries the Service Registry and routes each request to an available service instance.

The following diagram shows how communication takes place:
[![Service Discovery Server Side](https://www.baeldung.com/wp-content/uploads/sites/4/2022/01/Service-Discovery-Server-Side.png)](https://www.baeldung.com/wp-content/uploads/sites/4/2022/01/Service-Discovery-Server-Side.png)
In this approach, a dedicated actor, the Load Balancer, does the job of load balancing. This is the main advantage of this approach. Indeed, **creating this level of abstraction makes the Service Consumer lighter, as it doesn’t have to deal with the lookup procedure.** As a matter of fact, there’s no need to implement the discovery logic separately for each language and framework that the Service Consumer uses.

![](https://microservices.io/i/servicediscovery/server-side-discovery.jpg)