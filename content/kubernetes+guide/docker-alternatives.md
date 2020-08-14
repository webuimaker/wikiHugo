---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 8  # Order that this section will appear.
title: "DOCKER ALTERNATIVES"
titleColor: 
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---

While [Docker](/display/containers/docker+vs+vagrant) is the most widely used and recognized container technology, there are other technologies that either preceded Docker, emerged side-by-side with Docker, or have been introduced more recently. All follow a similar concept of images and containers, but have some technical difference worth understanding:

## rkt (pronounced 'rocket') from the Linux distributor, CoreOS

CoreOS released rkt in 2014, with a production-ready release in February 2016, as a more secure alternative to Docker. It is the most worthy alternative to Docker as it has the most real-world adoption, has a fairly big open source community, and is part of the CNCF. It was first released in February 2016.


**Additional reading:** {{< read-more "Product page" "https://coreos.com/rkt/" "_target" >}} , {{< read-more "GitHub page" "https://github.com/rkt/rkt" "_target" >}}

## LXD (pronounced “lexdi”) from Canonical Ltd., the company behind Ubuntu

Canonical launched its own Docker alternative, LXD, in November 2014, with the focus of offering full system containers. Basically, LXD acts like a container hypervisor and is more Operating System centric rather than Application Centric.

**Additional reading:** {{< read-more "Product page" "https://www.ubuntu.com/containers/lxd" "_target" >}} , {{< read-more "GitHub page" "https://github.com/lxc/lxd" "_target" >}}

## Linux VServer

Like OpenVZ, Linux VServer provides operating system-level virtualization capabilities via a patched Linux kernel. The first stable version was released in 2008.

**Additional reading:** {{< read-more "Website" "http://linux-vserver.org/Welcome_to_Linux-VServer.org" "_target" >}} , {{< read-more "GitHub page" "https://github.com/linux-vserver" "_target" >}}

## Windows Containers

Microsoft has also introduced the Windows Containers feature with the release of the Windows Server 2016, in September 2016. There are currently two Windows Container types:

- Windows Containers: Similar to Docker containers Windows containers use namespaces and resource limits to isolate processes from one another. These containers share a common kernel unlike a virtual machine which has its own kernel.
- Hyper-V Containers: Hyper-V containers are fully isolated highly optimized virtual machines that contain a copy of the windows Kernel. Unlike Docker containers that isolate processes and share the same kernel, Hyper-V containers each have their own kernel.

**See the** {{< read-more "Microsoft documentation" "https://docs.microsoft.com/en-us/virtualization/windowscontainers/about/" "_target" >}}







