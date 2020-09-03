---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 1  # Order that this section will appear.
title: "Containers vs. Virtual Machines"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"

---

When compared to Virtual machines, the Docker platform moves up the abstraction of resources from the hardware level to the Operating System level. This allows for the realization of the various benefits of Containers e.g. application portability, infrastructure separation, and self-contained microservices. In other words, while Virtual Machines abstract the entire hardware server, Containers abstract the Operating System kernel. This is a whole different approach to virtualization and results in much faster and more lightweight instances .

![Container vs. VM Implementation](/images/Container_VM_Implementation.png)




Container vs. VM Implementation



**For a more in-depth comparison between Dockers and VMs, see:** {{< read-more "Docker vs. Virtual Machines" "https://www.aquasec.com/wiki/display/containers/Docker+vs.+Virtual+Machines" "_target"  >}}

<strong>Advantages</strong>


The main advantages of Docker are:

* Resource Efficiency: Process level isolation and usage of the container host’s kernel is more efficient when compared to virtualizing an entire hardware server.

* Portability: All the dependencies for an application are bundled in the container. This means they can be easily moved between development, test, and production environments.

* Continuous Deployment and Testing: The ability to have consistent environments and flexibility with patching has made Docker a great choice for teams that want to move from waterfall to the modern DevOps approach to software delivery.