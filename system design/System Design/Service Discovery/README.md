**The Service Discovery mechanism helps us know where each instance is located. In this way, a Service Discovery component acts as a registry in which the addresses of all instances are tracked.** The instances have dynamically assigned network paths. Consequently, if a client wants to make a request to a service, it must use a Service Discovery mechanism.

## The Need for Service Discovery
**A microservice needs to know the location (IP address and port) of every service it communicates with.** If we don’t employ a Service Discovery mechanism, service locations become coupled, leading to a system that’s difficult to maintain. We could wire the locations or inject them via configuration in a traditional application, but it isn’t recommended in a modern cloud-based application of this kind.

**Dynamically determining the location of an application service isn’t a trivial matter. Things become more complicated when we consider an environment where we’re constantly destroying and distributing new instances of services.** This may well be the case for a cloud-based application that’s continuously changing due to horizontal autoscaling to meet peak loads, or the release of a new version. **Hence, the need for a Service Discovery mechanism.**

**Service Discovery handles things in two parts. First, it provides a mechanism for an instance to register and say, “_I’m here!_” Second, it provides a way to find the service once it has registered.**
![[ym3ifa2r.bmp]]

Let’s describe the steps illustrated in the diagram:

1. The location of the Service Provider is sent to the Service Registry (a database containing the locations of all available service instances).
2. The Service Consumer asks the Service Discovery Server for the location of the Service Provider.
3. The location of the Service Provider is searched by the Service Registry in its internal database and returned to the Service Consumer.
4. The Service Consumer can now make direct requests to the Service Provider.

There are two main Service Discovery patterns: Client‑Side Discovery and Server‑Side Discovery. Let’s clarify them.