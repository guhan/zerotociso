# DNS
Kubernetes creates DNS records for Services and Pods.

- A DNS query may return different results based on the namespace of the Pod making it. DNS queries that don't specify a namespace are limited to the Pod's namespace.

## Service DNS
SRV Records are created for named ports that are part of normal or headless services. For each named port, the SRV record has the form _port-name._port-protocol.my-svc.my-namespace.svc.cluster-domain.example. 

## Pod Hostname
```
apiVersion: v1
kind: Service
metadata:
  name: busybox-subdomain
spec:
  selector:
    name: busybox
  clusterIP: None
  ports:
  - name: foo # name is not required for single-port Services
    port: 1234
---
apiVersion: v1
kind: Pod
metadata:
  name: busybox1
  labels:
    name: busybox
spec:
  hostname: busybox-1
  subdomain: busybox-subdomain
  containers:
  - image: busybox:1.28
    command:
      - sleep
      - "3600"
    name: busybox
---
apiVersion: v1
kind: Pod
metadata:
  name: busybox2
  labels:
    name: busybox
spec:
  hostname: busybox-2
  subdomain: busybox-subdomain
  containers:
  - image: busybox:1.28
    command:
      - sleep
      - "3600"
    name: busybox
```


## Pod DNS Policy
Important to set these to address vulnerabilities like DNS hijacking. 

- "Default": The Pod inherits the name resolution configuration from the node that the Pods run on. See related discussion for more details.
- "ClusterFirst": Any DNS query that does not match the configured cluster domain suffix, such as "www.kubernetes.io", is forwarded to an upstream nameserver by the DNS server. Cluster administrators may have extra stub-domain and upstream DNS servers configured. See related discussion for details on how DNS queries are handled in those cases.
- "ClusterFirstWithHostNet": For Pods running with hostNetwork, you should explicitly set its DNS policy to "ClusterFirstWithHostNet". Otherwise, Pods running with hostNetwork and "ClusterFirst" will fallback to the behavior of the "Default" policy.
Note: This is not supported on Windows. See below for details
- "None": It allows a Pod to ignore DNS settings from the Kubernetes environment. All DNS settings are supposed to be provided using the dnsConfig field in the Pod Spec. See Pod's DNS config subsection below.
