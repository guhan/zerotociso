# Jobs and Cronjobs

## Jobs
A Job creates one or more Pods and will continue to retry execution of the Pods until a specified number of them successfully terminate. 
- As pods successfully complete, the Job tracks the successful completions.
- When a specified number of successful completions is reached, the task (ie, Job) is complete.
- Deleting a Job will clean up the Pods it created.When a Job completes, no more Pods are created, but the Pods are usually not deleted either. 
  - The TTL-after-finished controller is only supported for Jobs. You can use this mechanism to clean up finished Jobs (either Complete or Failed) automatically by specifying the .spec.ttlSecondsAfterFinished field of a Job
- Suspending a Job will delete its active Pods until the Job is resumed again.

```
apiVersion: batch/v1
kind: Job
metadata:
  name: pi
spec:
  template:
    spec:
      containers:
      - name: pi
        image: perl:5.34.0
        command: ["perl",  "-Mbignum=bpi", "-wle", "print bpi(2000)"]
      restartPolicy: Never
  backoffLimit: 4

```

## Cronjobs
A CronJob creates Jobs on a repeating schedule.

```
apiVersion: batch/v1
kind: CronJob
metadata:
  name: hello
spec:
  schedule: "* * * * *"
  jobTemplate:
    spec:
      template:
        spec:
          containers:
          - name: hello
            image: busybox:1.28
            imagePullPolicy: IfNotPresent
            command:
            - /bin/sh
            - -c
            - date; echo Hello from the Kubernetes cluster
          restartPolicy: OnFailure
```

