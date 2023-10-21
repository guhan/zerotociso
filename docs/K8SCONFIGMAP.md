# ConfigMap
A ConfigMap provides a way to inject configuration data into pods. The data stored in a ConfigMap can be referenced in a volume of type configMap and then consumed by containerized applications running in a pod.

- You must create a ConfigMap before you can use it.
- A ConfigMap is always mounted as readOnly.
- A container using a ConfigMap as a subPath volume mount will not receive ConfigMap updates.
- Text data is exposed as files using the UTF-8 character encoding. For other character encodings, use binaryData.

## Example
The following configuration shows how to mount the log-config ConfigMap onto a Pod called configmap-pod:

```
apiVersion: v1
kind: Pod
metadata:
  name: configmap-pod
spec:
  containers:
    - name: test
      image: busybox:1.28
      command: ['sh', '-c', 'echo "The app is running!" && tail -f /dev/null']
      volumeMounts:
        - name: config-vol
          mountPath: /etc/config
  volumes:
    - name: config-vol
      configMap:
        name: log-config
        items:
          - key: log_level
            path: log_level
```

The log-config ConfigMap is mounted as a volume, and all contents stored in its log_level entry are mounted into the Pod at path /etc/config/log_level. Note that this path is derived from the volume's mountPath and the path keyed with log_level.
