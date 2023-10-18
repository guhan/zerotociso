# Workloads

## Deployment 
- Stateless workload

## ReplicaSet 
- Multiple copies of the same type of pod
- (replacing the legacy resource ReplicationController). Deployment is a good fit for managing a stateless application workload on your cluster, where any Pod in the Deployment is interchangeable and can be replaced if needed.

## StatefulSet 
- designed to handle stateful workloads where each pod in the set has a unique identity and stable network identity.
- lets you run one or more related Pods that do track state somehow. For example, if your workload records data persistently, you can run a StatefulSet that matches each Pod with a PersistentVolume. Your code, running in the Pods for that StatefulSet, can replicate data to other Pods in the same StatefulSet to improve overall resilience.

## DaemonSet 
- Runs on each node
- defines Pods that provide facilities that are local to nodes. Every time you add a node to your cluster that matches the specification in a DaemonSet, the control plane schedules a Pod for that DaemonSet onto the new node. Each pod in a DaemonSet performs a job similar to a system daemon on a classic Unix / POSIX server. A DaemonSet might be fundamental to the operation of your cluster, such as a plugin to run cluster networking, it might help you to manage the node, or it could provide optional behavior that enhances the container platform you are running.

## Job 
provide different ways to define tasks that run to completion and then stop. You can use a Job to define a task that runs to completion, just once. 

## Cronjob
You can use a CronJob to run the same Job multiple times according a schedule.
