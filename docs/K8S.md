# Kubernetes (k8s)
Kubernetes is a container orchestration platform that is cloud agnostic (works in AWS, GCP, Azure). 

![K8s Overview](/images/k8s-overview.png)

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
  - supports container runtimes such as Docker, containerd, CRI-O
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





## Leases
- Leases can be thought of as distributed locks (aka lockfile)
- Leases have a time-to-live (TTL) associated with them, after which they expire.
- When a Lease expires or is released, another pod or component can acquire it

## Workloads
- **Deployment**: Deployment is a good fit for managing a stateless application workload on your cluster, where any Pod in the Deployment is interchangeable and can be replaced if needed.
- **ReplicaSet**:
- **StatefulSet**: lets you run one or more related Pods that do track state somehow. For example, if your workload records data persistently, you can run a StatefulSet that matches each Pod with a PersistentVolume. Your code, running in the Pods for that StatefulSet, can replicate data to other Pods in the same StatefulSet to improve overall resilience.
- **DaemonSet**: defines Pods that provide facilities that are local to nodes. Every time you add a node to your cluster that matches the specification in a DaemonSet, the control plane schedules a Pod for that DaemonSet onto the new node. Each pod in a DaemonSet performs a job similar to a system daemon on a classic Unix / POSIX server. A DaemonSet might be fundamental to the operation of your cluster, such as a plugin to run cluster networking, it might help you to manage the node, or it could provide optional behavior that enhances the container platform you are running.
- **Job**: define a task that runs to completion
- **CronJob**: run the same Job multiple times according a schedule.



