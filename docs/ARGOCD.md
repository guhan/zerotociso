# Argo CD
ArgoCD is an open-source declarative continuous delivery tool for Kubernetes applications. It is part of the Argo project, which includes several tools designed to help with workflows and deployments on Kubernetes. ArgoCD specifically focuses on automating the deployment and lifecycle management of applications in Kubernetes clusters.

## Declarative Configuration
ArgoCD uses a declarative approach to describe the desired state of your applications in a Git repository. This allows you to manage your application configurations as code.
## GitOps
ArgoCD follows the GitOps methodology, where the desired state of your applications is specified in a Git repository. Changes to the Git repository trigger ArgoCD to reconcile the actual state with the declared state, ensuring that the applications in the Kubernetes cluster match the desired configuration.
## Multi-Cluster Support
ArgoCD supports the management of applications across multiple Kubernetes clusters. This is useful in scenarios where you have a distributed or hybrid infrastructure.
## Application Rollouts and Rollbacks
ArgoCD facilitates controlled rollouts of application changes and provides the ability to rollback to a previous version if needed.
## Web UI and CLI
ArgoCD provides a web-based user interface (UI) and a command-line interface (CLI) for managing and monitoring applications.
## Health and Sync Status
ArgoCD monitors the health and synchronization status of applications, providing insights into the current state and health of your deployments.
## Integration with CI/CD
ArgoCD can be integrated into continuous integration and continuous delivery (CI/CD) pipelines to automate the deployment process.
## Extensibility
ArgoCD is extensible and supports custom resource definitions (CRDs) for defining and managing applications.

## Argo CD Architecture
Argo CD is implemented as a kubernetes controller which continuously monitors running applications and compares the current, live state against the desired target state (as specified in the Git repo). A deployed application whose live state deviates from the target state is considered OutOfSync. Argo CD reports & visualizes the differences, while providing facilities to automatically or manually sync the live state back to the desired target state. Any modifications made to the desired target state in the Git repo can be automatically applied and reflected in the specified target environments.

![ArgoCD](/images/ARGOCD.png)

### API Server¶

The API server is a gRPC/REST server which exposes the API consumed by the Web UI, CLI, and CI/CD systems. It has the following responsibilities:

- application management and status reporting
- invoking of application operations (e.g. sync, rollback, user-defined actions)
- repository and cluster credential management (stored as K8s secrets)
- authentication and auth delegation to external identity providers
- RBAC enforcement
- listener/forwarder for Git webhook events

### Repository Server¶

The repository server is an internal service which maintains a local cache of the Git repository holding the application manifests. It is responsible for generating and returning the Kubernetes manifests when provided the following inputs:

- repository URL
- revision (commit, tag, branch)
- application path
- template specific settings: parameters, helm values.yaml

### Application Controller¶

The application controller is a Kubernetes controller which continuously monitors running applications and compares the current, live state against the desired target state (as specified in the repo). It detects OutOfSync application state and optionally takes corrective action. It is responsible for invoking any user-defined hooks for lifecycle events (PreSync, Sync, PostSync)
