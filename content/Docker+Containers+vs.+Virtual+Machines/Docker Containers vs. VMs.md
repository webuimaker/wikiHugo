---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 6  # Order that this section will appear.
title: "Docker Containers vs. VMs"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
At last, we arrive at the big question: how are the two different? It all comes down to what you want to do with them. Below, we’ll mention a few advantages of Docker as opposed to a virtual machine (specifically Docker vs. VMware), and vice versa.

{{< table >}}
<table>
<tr><th>Pricing comparison</th></tr>
<tr><td>**Docker**: Free. Enterprise Edition starts at $750/node/year.</td></tr>
<tr><td>**VMware vSphere**: Standard license starts at $995.</td></tr>
</table>
{{< /table >}}

For more details and a Docker vs VM comparison, see this page by [UpGuard](https://www.upguard.com/articles/docker-vs.-vmware-how-do-they-stack-up).

## Advantages of Virtual Machines

* The tools associated with a virtual machine are easier to access and simpler to work with. Docker has a more complicated tooling ecosystem, that consists of both Docker-managed and third-party tools.

* As mentioned earlier, once you have a virtual machine up and running, you can start a Docker instance within that VM, and [run docker container](/display/containers/Running+Docker+Containers) within the VM (which is the predominant method of running containers at present). This way, containers and virtual machines are not mutually exclusive and can co-exist alongside each other.

## Advantages of Docker Containers

* Docker containers are process-isolated and don’t require a hardware hypervisor. This means Docker containers are much smaller and require far fewer resources than a VM.

* Docker is fast. Very fast. While a VM can take an at least a few minutes to boot and be dev-ready, it takes anywhere from a few milliseconds to (at most) a few seconds to [start a Docker container](/display/containers/Starting+and+Restarting+Docker+Containers+Automatically) from a container image.

* Containers can be shared across multiple team members, bringing much-needed portability across the development pipeline. This reduces ‘works on my machine’ errors that plague [DevOps](/display/containers/The+Shift+Left+Principle+and+DevOps) teams.



**For more details, see an in-depth discussion:** {{< read-more "How containers and VM are different" "https://stackoverflow.com/questions/16047306/how-is-docker-different-from-a-normal-virtual-machine" "_target"  >}}	




The road ahead is quickly changing for VMs at least, as Docker is quickly rising in popularity among major corporations. It’s clear that speed and efficiency are the biggest needs for DevOps teams, and Docker is better at providing these over VMs. While it still hasn’t completely replaced virtual machines in production environments, Docker's potential is being noticed. That isn’t to say that VMs will soon be gone. Rather, Docker and VMs will co-exist next to each other, giving DevOps teams more choices in how to run their cloud-native applications.










