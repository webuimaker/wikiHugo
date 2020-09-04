---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 4  # Order that this section will appear.
title: "Take an Integrated Approach to Security"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
Container security is perhaps the most important concern for organizations running Docker in production. This is because containers are completely different from traditional VMs. They can’t be adequately secured with a Docker-provided security tool, as Docker itself doesn’t have a hold on the entire container ecosystem. Instead, you need to take a best-of-breed approach to integrate specialist tools that excel in a particular aspect of container security and ensure segregation of duties between those who create and run containers on the one hand, and those who create, monitor and enforce security policy on the other.

The first step is to understand how Docker differs from a VM, and what this means for security. Docker inherits many kernel-level security features from Linux. This includes features like namespaces and cgroups which restrict a container’s access to its neighboring containers and limit its use of system resources.

A level above that, you need to monitor and control the usage of container images. This requires scanning of images downloaded from a registry like Docker Hub. You ideally want to allow only official and vetted images to be downloaded and shared within your organization. Access and permission control needs to be monitored to ensure only those who need access to a container have it, and others don’t. The principle of least privilege is paramount here. The CIS Docker benchmark is a great standard to measure how secure your system is as it covers many aspects of securing containers in production.

Along with these efforts, you need a dedicated container security tool that can automatically track violations and concerns across your Docker stack end-to-end. [Aqua Security](https://www.aquasec.com/) is one such platform that delivers threat detection during runtime and is able to spot intrusions or vulnerabilities from within before they escalate and cause large-scale damage.

> In conclusion, running Docker in production is a very attractive proposition, but there are many ways it can go wrong. But by following the right approach and focussing on important aspects like application architecture, container orchestration, container networking, and container security you can enjoy the benefits of Docker without risking its potential pitfalls. As we move into a world of increasingly Dockerized applications, having the right approach and tools will give you the edge when running Docker in production.