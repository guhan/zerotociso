# Secrets
In Kubernetes, a Secret is an object that is used to store and manage sensitive information, such as passwords, API keys, and other confidential data. Secrets provide a way to securely handle and distribute such information to containers within pods or to be used by other parts of the system.

## Data Types
A Secret can store key-value pairs, where both the keys and values are encoded as byte arrays. Common use cases include storing data like usernames, passwords, and tokens.
## Base64 Encoding
The data in a Secret is base64 encoded. While this encoding provides a basic level of obfuscation, it's essential to note that Kubernetes Secrets are not a foolproof security mechanism. They provide a layer of convenience but should not be solely relied upon for strong security.
## Pod Access
Secrets can be mounted into the file system of a pod as a volume or exposed as environment variables. This allows containers within the pod to access the sensitive information.
## Immutability
Once a Secret is created, it is immutable. To update the data stored in a Secret, you generally create a new Secret with the updated information.
## Name and Namespace
Secrets are scoped to a specific namespace within Kubernetes, and they have a unique name within that namespace.

## Example
Creating a secret

```
apiVersion: v1
kind: Secret
metadata:
  name: my-secret
type: Opaque
data:
  username: dXNlcm5hbWU=   # base64 encoded "username"
  password: cGFzc3dvcmQ=   # base64 encoded "password"
```

Using a secret in a pod as an environment variable

```
apiVersion: v1
kind: Pod
metadata:
  name: mypod
spec:
  containers:
  - name: mycontainer
    image: myimage
    env:
      - name: MY_USERNAME
        valueFrom:
          secretKeyRef:
            name: my-secret
            key: username
      - name: MY_PASSWORD
        valueFrom:
          secretKeyRef:
            name: my-secret
            key: password
```




