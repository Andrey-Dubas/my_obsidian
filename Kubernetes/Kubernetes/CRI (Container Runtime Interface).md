[[CRI (Container Runtime Interface)]] is a collection gRPC API, specs/requirements and libraries for container runtimes to integrate with kubelet.

Kubelet can talk with [[CRI (Container Runtime Interface)]]-compliant container runtime.


![[CRI (Container Runtime Interface) 2024-07-05 15.52.47.excalidraw]]


A container runtime shim is **a piece of software that resides in between a container manager (containerd, cri-o, podman) and a container runtime (runc, crun) solving the integration problem of these counterparts**.
For example, comtainer's manager (runc?) might crash, but stdin and stdout  of container.
