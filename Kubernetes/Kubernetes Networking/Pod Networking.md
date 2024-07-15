
The diagram that describes the relationship between pod, host, and the global internet at the networking level via veth0:

![[Pod Networking 2024-07-05 17.54.23.excalidraw]]

[[Kubenet]] is a kubernetes network plugin. It creates a network bridge cbr0 and veth device.

[[CNI (Container Networking Interface)]] is a specification as well as a set of libraries for writing network plugins to configure network interfaces in linux containers (not just Docker).

[[CNI (Container Networking Interface)]] defines a plugin spec for networking application containers, but the plugin must be plugged into a container runtime that provides some services. For kubernetes, each pod has its own IP address, and the pod is the [[CNI (Container Networking Interface)]] container, not the containers within the pod.