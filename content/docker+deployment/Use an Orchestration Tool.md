---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 2  # Order that this section will appear.
title: "Use an Orchestration Tool"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
The next step is to use a powerful orchestration tool like [Kubernetes](/display/containers/kubernetes+guide). With the many moving parts of a dynamic Docker stack, a container orchestration platform is able to provide a layer of abstraction between the containers and the infrastructure that powers them.

Kubernetes is a powerful tool that automates and simplifies the creation and management of container resources. It has been going through rapid evolution and recent updates like role-based access control (RBAC), and [secrets](/display/containers/container+secrets+management) encryption are making it even more capable of running production workloads.

There are other orchestration tools like [Swarm](/display/containers/docker+swarm+101) and Mesos, but Kubernetes is winning this battle because of its extensibility, long feature list, and large open source community. As you look to take Docker into production, an orchestration tool like Kubernetes is a must-have.