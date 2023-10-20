# Endpoint Slice
EndpointSlice contains references to a set of network endpoints.
- include references to all the Pods that match the Service selector.
- EndpointSlices group network endpoints together by unique combinations of protocol, port number, and Service name.
- The name of a EndpointSlice object must be a valid DNS subdomain name

## Example
```
apiVersion: discovery.k8s.io/v1
kind: EndpointSlice
metadata:
  name: example-abc
  labels:
    kubernetes.io/service-name: example
addressType: IPv4
ports:
  - name: http
    protocol: TCP
    port: 80
endpoints:
  - addresses:
      - "10.1.2.3"
    conditions:
      ready: true
    hostname: pod-1
    nodeName: node-1
    zone: us-west2-a
```
