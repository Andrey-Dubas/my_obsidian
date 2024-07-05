The Service Registry is a crucial part of service identification. It is a database containing the network locations of service instances. A Service Registry must be highly available and up-to-date.
A Service Registry consists of a cluster of servers that use a replication protocol to maintain consistency.

## Self-Registration
When using self-registration model, a service instance is responsible for registering and de-registering itself in the Service Registry. In addition. if necessary, a service instance sends heartbeat requests to keep its registration alive.
[![Service Discovery Self Registration](https://www.baeldung.com/wp-content/uploads/sites/4/2022/01/Service-Discovery-Self-Registration.png)](https://www.baeldung.com/wp-content/uploads/sites/4/2022/01/Service-Discovery-Self-Registration.png)

The self-registration model has several pros and cons. One advantage is that it’s relatively simple and doesn’t require other system components as intermediaries. However, a significant disadvantage is that it couples service instances to the Service Registry, which means we must implement the registration code in each language and framework used.

An alternate approach, which decouples services from the Service Registry, is the third-party registration scheme.

## 3-rd Party registration
When using the 3rd party registration model, the service instances aren't responsible for registration in the Service Registry. Instead, another system component known as the [[Service Register]] is responsible registration. The [[Service Register]] keeps track of changes to running instances by polling the deployment environment or subscribing to events. When it detects a newly available service instance, it records it in its database. The [[Service Registry]] also de-registers terminated service instances.
[![Service Discovery 3rd Registration](https://www.baeldung.com/wp-content/uploads/sites/4/2022/01/Service-Discovery-3rd-Registration.png)](https://www.baeldung.com/wp-content/uploads/sites/4/2022/01/Service-Discovery-3rd-Registration.png)

One disadvantage of this model is that, unless it’s embedded in the deployment environment, it’s yet another highly available system component that needs to be set up and managed.