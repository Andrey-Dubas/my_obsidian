[[Kube scheduler]] is responsible for scheduling pods into nodes. This is a very complicated task as it needs to consider multiple factors:
 - Resource availability
 - Service requirements
 - affinity, anti-affinity
 - ...
==Can be replaced with custom scheduler==