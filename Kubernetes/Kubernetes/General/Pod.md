All the containers in a pod have the same IP address and port space; they can communicate using localhost or inter-process communication.

Each pod contains one OR MORE containers.  

Pods are considered ephemeral, throwaway entities that can be discarded and replaced at will. Any pod storage is destroyed with its pod, Each pod gets a unique ID