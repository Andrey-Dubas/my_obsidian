[[External Load Balancer]] operate at the node level; While they  direct traffic to a particular pod, the load distribution is done at the node level. This means  that if your service has four pods and three of them are on node A and the last one is on node B, then [[External Load Balancer]] likely to divide  the load evenly between node A and node B. This will  have three pods on node A handle half of the load.