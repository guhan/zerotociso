# Pods
- a group of one or more containers
- Pods are designed as relatively ephemeral, disposable entities
- Pods that wish to connect to the API server can do so securely by leveraging a service account so that Kubernetes will automatically inject the public root certificate and a valid bearer token into the pod when it is instantiated
- A Pod's contents are always co-located and co-scheduled, and run in a shared context
- The name of a Pod must be a valid DNS subdomain value
- Each Pod is assigned a unique IP address for each address family.

## Networking
- Each Pod is assigned a unique IP address for each address family.
- Every container in a Pod shares the network namespace, including the IP address and network ports.
  
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
