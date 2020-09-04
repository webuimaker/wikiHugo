---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 2  # Order that this section will appear.
title: "Docker Architecture"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---



To allow for an application to be self-contained the Docker approach moves up the abstraction of resources from the hardware level to the Operating System level.

To further understand Docker, let us look at its architecture. It uses a client-server model and comprises of the following components:

* <strong>Docker daemon:</strong> The daemon is responsible for all container related actions and receives commands via the CLI or the REST API.

* <strong>Docker Client:</strong> A Docker client is how users interact with Docker. The Docker client can reside on the same host as the daemon or a remote host.

* <strong>Docker Objects:</strong> Objects are used to assemble an application. Apart from networks, volumes, services, and other objects the two main requisite objects are:

* <strong>Images:</strong> The read-only template used to build containers. Images are used to store and ship applications.

* <strong>Containers:</strong> Containers are encapsulated environments in which applications are run. A container is defined by the image and configuration options. At a lower level, you have [containerd](/display/containers/containerd), which is a core container runtime that initiates and supervises container performance.

* <strong>Docker Registries:</strong> Registries are locations from where we store and download (or “pull”) images.



![alt](/images/docker-architecture.png)





Source:  [NordicAPIs.com](http://NordicAPIs.com)


