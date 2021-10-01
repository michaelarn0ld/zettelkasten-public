# What's a Container and Why Should You Care?


## What's a Container?
* A container bundles an application's code together with the related 
configuration files and libraries, and dependencies required for it to run.
* Containerized applications are isolated in that they do not bundle in a copy
of the OS. Instead an open source runtime engine (Docker in our case) is
installed on the host OS and becomes a the conduit by which containers share the
OS with other containers on the same computing system.


## Why Containers?
* Containers allow developers to deploy applications seamlessly across platforms
because the contents of the container are abstracted away from the host OS.
* Containers allow applications to be "written once and run anywhere", which
speeds development and prevents cloud-vendor "lock in".
* Containers are lightweight because they share the machine's OS kernel and are
not bogged down with the extra overhead of an entire OS.
* Containers are secure as their inherent isolation prevents the invasion of
malicious code from affecting other containers or the host OS.


## Containers vs Virtual Machines
* VMs virtualize the underlying hardware so that multiple OS instances can run
on the hardware. Each VM runs its own OS and has access to virtualized resources
representing the underlying hardware.
* Due to the nature of VMs, you can run different operating systems on the same
machine; however, each VM contains an OS image, libraries, applications, etc and
therefore can become quite large.
* Containers virtualize the underlying OS and cause the containerized app to 
percieve that it has the OS (including CPU, memory, file storage) all to itself.
* Containers do not need to boot an OS or load libraries because they share the
host OS.
* Containers are lightweight and fast and when compared to VMs, many more
instances of an application can fit onto the same machine.
* The major constraint of containers is the operating system which they are
defined for; a container or Linux can't run on Windows and vice versa.


## Related
[202110010145](../202110010145) - Containers are to Programs as Kubernetes is to Operating System


## Tags
#containers #containerization #docker #virtualization
