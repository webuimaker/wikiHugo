---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 1  # Order that this section will appear.
title: "What is Docker?"
titleColor: "#003366"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"

---

You probably heard of the statement ‘Write once, run anywhere’, a catchphrase that SUN Microsystems came out with to capture Java’s ubiquitous nature. This is a great paradigm except that, if you have a java application, for example, in order to run it anywhere you need platform-specific implementations of the Java Virtual Machine. On the other end of the ‘run anywhere’ spectrum, we have [Virtual Machines](/display/containers/Docker+Containers+vs.+Virtual+Machines). This approach, while versatile, comes at the cost of large image sizes, high IO overhead, and maintenance costs. 

What if there is something that is light in terms of storage, abstracted enough to be run anywhere, and independent of the language used for development?


This is where [Docker](/display/containers/Docker+Containers) comes in! Docker is a technology that allows you to incorporate and store your code and its dependencies into a neat little package - an image. This image can then be used to spawn an instance of your application - a container. The fundamental difference between containers and Virtual Machines is that containers don’t contain a hardware hypervisor.

![confluence-embedded-file-wrapper confluence-embedded-manual-size](/images/docker-containers.png)

This approach takes care of several issues:

- No platform specific, IDE, or programming language restrictions.
- Small image sizes, making it easier to ship and store.
- No compatibility issues relating to the dependencies/versions/setup.
- Quick and easy application instance deployment.
- Applications and their resources are isolated, leading to better modularity and security.
