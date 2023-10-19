# Pods
- a group of one or more containers that _ideally_ share related workloads
- has a unique UID
- Pods are designed as relatively ephemeral, disposable entities
- Pods that wish to connect to the API server can do so securely by leveraging a service account so that Kubernetes will automatically inject the public root certificate and a valid bearer token into the pod when it is instantiated
- A Pod's contents are always co-located and co-scheduled, and run in a shared context



## Networking
- Each Pod is assigned a unique IP address for each address family.
- Every container in a Pod shares the network namespace, including the IP address and network ports.
- The name of a Pod must be a valid DNS subdomain value
    
```
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  containers:
  - name: nginx
    image: nginx:1.14.2
    ports:
    - containerPort: 80
```

## Status (i.e. Pod phase)
- **Pending**	The Pod has been accepted by the Kubernetes cluster, but one or more of the containers has not been set up and made ready to run. This includes time a Pod spends waiting to be scheduled as well as the time spent downloading container images over the network.
- **Running**	The Pod has been bound to a node, and _all_ of the containers have been created. At least one container is still running, or is in the process of starting or restarting.
- **Succeeded**	All containers in the Pod have terminated in success, and will not be restarted.
- **Failed**	All containers in the Pod have terminated, and at least one container has terminated in failure. That is, the container either exited with non-zero status or was terminated by the system.
- **Unknown**	For some reason the state of the Pod could not be obtained. This phase typically occurs due to an error in communicating with the node where the Pod should be running.
- **Terminating** When a Pod is being deleted, it is shown as Terminating by some kubectl commands. This Terminating status is _not_ one of the Pod phases. A Pod is granted a term to terminate gracefully, which defaults to 30 seconds. You can use the flag --force to terminate a Pod by force.

## Static pods
Static Pods are managed directly by the kubelet daemon on a specific node, without the API server observing them. Unlike Pods that are managed by the control plane (for example, a Deployment); instead, the kubelet watches each static Pod (and restarts it if it fails).

- Static Pods are always bound to one Kubelet on a specific node.

- The kubelet automatically tries to create a mirror Pod on the Kubernetes API server for each static Pod. This means that the Pods running on a node are visible on the API server, but cannot be controlled from there.
- The Pod names will be suffixed with the node hostname with a leading hyphen.


