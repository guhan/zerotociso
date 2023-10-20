# Networking

- Every Pod in a cluster gets its own unique cluster-wide IP address.
- pods can communicate with all other pods on any other node without NAT
- agents on a node (e.g. system daemons, kubelet) can communicate with all pods on that node
- containers within a Pod can all reach each other's ports on localhost. This also means that containers within a Pod must coordinate port usage,
