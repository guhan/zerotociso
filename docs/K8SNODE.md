# Nodes
kubelet will either automatilly register the node or someone can manually add one
```
{
  "kind": "Node",
  "apiVersion": "v1",
  "metadata": {
    "name": "10.240.79.157",
    "labels": {
      "name": "my-first-k8s-node"
    }
  }
}
```
- name of a Node object must be a valid DNS subdomain name.
- To mark a Node unschedulable, run:
  ```kubectl cordon $NODENAME```
- You can use kubectl to view a Node's status and other details:
  ```kubectl describe node <insert-node-name-here>```
- Heartbeats, sent by Kubernetes nodes, help your cluster determine the availability of each node
- Nodes should be provisioned with the public root certificate for the cluster such that they can connect securely to the API server along with valid client credentials.
