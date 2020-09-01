---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 6  # Order that this section will appear.
title: "Docker Networking with Multiple Hosts"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
When working with multi-host, there is a need to use higher-level Docker orchestration tools to ease management of networking between a cluster of machines. Popular orchestration tools today include [Docker Swarm](/display/containers/Docker+Swarm+101), Kubernetes, and Apache Mesos.

## Docker Swarm

[Docker Swarm](/display/containers/Docker+Swarm+101) is a Docker Inc. native tool used to orchestrate Docker containers. It enables you to manage a cluster of hosts as a single resource pool.

Docker Swarm makes use of overlay networks for inter-host communication. The swarm manager service is responsible for automatically assigning IP addresses to the containers.

For service discovery, each service in the swarm gets assigned a unique DNS name. Additionally, Docker Swarm has an embedded DNS server. You can query every container running in the swarm through this embedded DNS server.

**See Docker Documentation:** {{< read-more "Manage swarm service networks" "https://docs.docker.com/engine/swarm/networking/" "_blank" >}}

## Kubernetes

[Kubernetes Guide](/display/containers/Kubernetes+Guide) is a system used for automating deployment, scaling, and management of containerized applications, either on a single host or across a cluster of hosts.

Kubernetes approaches networking in a different way as compared to Docker, using native concepts like services and pods. Each pod has an IP address and no linking of pods is required, neither do you need to explicitly map container ports to host ports. There are DNS-based service discovery plugins which can be used for service discovery.
Apache Mesos
Apache Mesos is an open-source project used to manage a cluster of containers, providing efficient resource sharing and isolation across distributed applications.

Mesos uses IP address management (IPAM) server and client to manage containers networking. The role of the IPAM server is to assign IP addresses on demand while the IPAM client acts as a bridge between a network isolator module and the IPAM server. A network isolator module is a lightweight module that’s loaded into the Mesos agent. It looks at scheduler task requirements and uses IPAM and network isolator services to provide IP addresses to the containers.

Mesos-dns is a DNS-based service discovery for Mesos. It allows applications and services running on Mesos to find each other through the DNS service.