# Kubernetes (k8s)
Kubernetes is a container orchestration platform that is cloud agnostic (works in AWS, GCP, Azure). 

## Benefits of using k8s
- **Service discovery and load balancing**: Kubernetes can expose a container using the DNS name or using their own IP address. If traffic to a container is high, Kubernetes is able to load balance and distribute the network traffic so that the deployment is stable.
- **Storage orchestration**: Kubernetes allows you to automatically mount a storage system of your choice, such as local storages, public cloud providers, and more.
- **Automated rollouts and rollbacks**: You can describe the desired state for your deployed containers using Kubernetes, and it can change the actual state to the desired state at a controlled rate. For example, you can automate Kubernetes to create new containers for your deployment, remove existing containers and adopt all their resources to the new container.
- **Automatic bin packing**: You provide Kubernetes with a cluster of nodes that it can use to run containerized tasks. You tell Kubernetes how much CPU and memory (RAM) each container needs. Kubernetes can fit containers onto your nodes to make the best use of your resources.
- **Self-healing**: Kubernetes restarts containers that fail, replaces containers, kills containers that don't respond to your user-defined health check, and doesn't advertise them to clients until they are ready to serve.
- **Secret and configuration management** Kubernetes lets you store and manage sensitive information, such as passwords, OAuth tokens, and SSH keys. You can deploy and update secrets and application configuration without rebuilding your container images, and without exposing secrets in your stack configuration.

## Components of k8s
![k8s](/images/k8s.png)

At a minimum you need a master node (instance) and two worker nodes (instances). 

### Master Node
- **kube-api-server**:
  - The API server is the front end for the Kubernetes control plane.
  - kube-apiserver is designed to scale horizontally—that is, it scales by deploying more instances.
    
- **kube-controller-manager**: runs the following control processes
  - **Node controller**: 
    - Responsible for noticing and responding when nodes go down.
    - checks the state of each node every 5 seconds
    - assigning a CIDR block to the node when it is registered 
  - **Job controller**: Watches for Job objects that represent one-off tasks, then creates Pods to run those tasks to completion.
    - Job is a Kubernetes resource that runs a Pod, or perhaps several Pods, to carry out a task and then stop.
  - **EndpointSlice controller**: Populates EndpointSlice objects (to provide a link between Services and Pods).
  - **ServiceAccount controller**: Create default ServiceAccounts for new namespaces.

- **kube-scheduler**:
  - Control plane component that watches for newly created Pods with no assigned node, and selects a node for them to run on.
  - checks that the sum of the requests of containers on the node is no greater than the node's capacity
    
- **etcd**:
  - Consistent and highly-available key value store
  - Used as Kubernetes' backing store for all cluster data.

### Worker Nodes
- **Container runtime**:
  - responsible for managing the execution and lifecycle of containers within the Kubernetes environment.
  - supports container runtimes such as containerd, CRI-O
- **kubelet**:
  - An agent that runs on each node in the cluster.
  - It makes sure that containers are running in a Pod.
- **kube-proxy**
  - a network proxy that runs on each node in your cluster
  - maintains network rules that allow network communication to your Pods from network sessions inside or outside of your cluster
- **Pods**: one or more containers


## k8s Addons
- **Cluster DNS**: Cluster DNS is a DNS server, in addition to the other DNS server(s) in your environment, which serves DNS records for Kubernetes services
- **Dashboard**: Dashboard is a general purpose, web-based UI for Kubernetes clusters.
- **Container Resource Monitoring**:
  - **metrics-server**:  discovers all nodes on the cluster and queries each node's kubelet for CPU and memory usage.
- **cluster-level logging**: a mechanism responsible for saving container logs to a central log store with search/browsing interface
- **Network plugins**:  are software components that implement the container network interface (CNI) specification. They are responsible for allocating IP addresses to pods and enabling them to communicate with each other within the cluster.

## Nodes
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


## Pods


- Pods that wish to connect to the API server can do so securely by leveraging a service account so that Kubernetes will automatically inject the public root certificate and a valid bearer token into the pod when it is instantiated


## Leases
- Leases can be thought of as distributed locks (aka lockfile)
- Leases have a time-to-live (TTL) associated with them, after which they expire.
- When a Lease expires or is released, another pod or component can acquire it


## How to secure k8s?

### Strong Authentication and Authorization:
- Implement strong authentication mechanisms, such as using certificates or external identity providers, to ensure only authorized users can access the cluster.
- Enable Role-Based Access Control (RBAC) to define granular access policies and restrict privileges based on user roles and responsibilities.


### Secure Kubernetes Components:
- Regularly update and patch the Kubernetes control plane components, including the API server, etcd, kubelet, and kube-proxy, to protect against known vulnerabilities.
- Securely configure the Kubernetes API server by enabling secure communication, disabling insecure APIs, and setting appropriate access controls.
- Protect the etcd data store by enabling encryption at rest, using access controls, and implementing network security measures.


### Network Security:
- Implement network policies and use network segmentation to control traffic flow between different components and namespaces.
- Apply security groups, firewalls, and network policies at the infrastructure level to restrict access to Kubernetes nodes and control traffic flow in and out of the cluster.


### Container Security:
- Use trusted container images from trusted sources and regularly update them to include the latest security patches.
- Implement container image scanning and vulnerability management tools to detect and remediate security issues in container images.
- Enforce pod security policies to control the security-related attributes of pods, such as privileged access, host namespace sharing, and resource usage.


### Monitoring and Logging:
- Implement centralized logging and monitoring solutions to collect and analyze logs from Kubernetes components, pods, and applications.
- Set up alerts and anomaly detection mechanisms to identify potential security incidents or abnormal behavior.
- Regularly review logs and monitor for unauthorized access attempts, suspicious activities, or other security-related events.


### Secure Communication:
- Enable encryption for communication within the cluster by using Transport Layer Security (TLS) certificates and mutual authentication.
- Utilize secure communication protocols (e.g., HTTPS) for communication with the Kubernetes API server and other external services.


### Regular Auditing and Penetration Testing:
- Conduct regular security audits and penetration testing to identify vulnerabilities and security weaknesses.
- Perform vulnerability scanning and assess the security posture of the Kubernetes environment to identify potential risks.


### Ongoing Education and Best Practices:
- Stay informed about the latest Kubernetes security best practices, security updates, and patches.
- Educate your team about secure coding practices, container security, and the proper configuration of Kubernetes components.
