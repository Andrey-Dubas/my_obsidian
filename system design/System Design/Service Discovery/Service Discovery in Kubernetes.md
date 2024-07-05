### Server-side Service Discovery

Kubernetes server-side discovery is a service discovery method that involves using the Kubernetes API server to discover and manage services. In the server-side discovery method, services are registered with the Kubernetes API server, which acts as a central registry for services.

Server-side discovery is a simple and straightforward method for service discovery in Kubernetes. It requires no additional infrastructure or tooling beyond the Kubernetes API server, and is easy to configure and manage.

Instance IPs can change without warning, making direct communication between services unpredictable. An Intermediary such as a load balancer may be more reliable and promote better service discovery.

The load balancer or reverse proxy sits in front of a group of instances and constitutes a single service. From perspective of the client, because the service discovery happens completely on the server-side, accessing the multi-instance services just like accessing a single network endpoint.

The client makes an initial network request, triggering the server-side service discovery process. Kubernetes routes the request to a load balancer. However, not providing the right information may lead to making poor routing decisions; this is why the load balancer relies on the [[Service Registry]] to track and communicate with instances and relay their statuses.

### Client-side Service Discovery

Kubernetes client-side discovery is a service discovery method that involves embedding service discovery logic in client applications. In this method, clients use a discovery mechanism to locate services. Unlike server-side discovery, which relies on the Kubernetes API server to manage service discovery, client-side discovery is more flexible since clients can choose which services to discover and how to discover them. In client-side discovery, the client retains the service registry and directly looks up the available service instance addresses in the registry.

By retaining the service registry and removing the load balancer from the equation in an attempt to improve service discovery, we arrive at client-side discovery. In practice, the most famous real-world example of client-side service discovery is the Netflix Eureka project.


**ExternalName** enables internal clients to utilize a Service's DNS name as an alias for an external DNS name, effectively providing an internal alias for the external DNS name.

Example YAML configuration for an ExternalName service:  

```
apiVersion: v1
kind: Service
metadata:
  name: my-service
spec:
  type: ExternalName
  externalName: external-service.example.com
```


### Envoy sidecar proxy

Envoy is a high-performance, open-source proxy that can be deployed as a sidecar to the application container in Kubernetes. Envoy can be used to handle the network traffic for the application, including load balancing, service discovery, and routing.  
When deployed as a sidecar, it can communicate with other sidecars in the same pod to manage traffic between the containers. This allows for more fine-grained control of the network traffic, including features such as circuit breaking and retries.  
Envoy is a popular choice for Kubernetes because it is designed to work well in cloud-native environments. It is scalable, fast, and supports advanced features such as rate limiting, service mesh integration, and TLS termination.
