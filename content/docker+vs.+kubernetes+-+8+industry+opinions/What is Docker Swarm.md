---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 2  # Order that this section will appear.
title: "What is Docker Swarm"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---

[Docker swarm](/display/containers/docker+swarm+101) mode allows you to manage a cluster of Docker Engines, natively within the Docker platform. You can use the Docker CLI to create a swarm, deploy application services to a swarm, and manage swarm behavior.

> **Note #1:** When people compare Kubernetes to Docker, they typically mean to compare it to Docker Swarm, the container orchestration engine offered within the Docker platform. It is not accurate to compare Kubernetes to "docker", the Docker Container Engine, because they have different functions. Kubernetes or Docker Swarm work together with the Docker Container Engine - the former manage and orchestrate containers, and the Docker Engine runs the containers themselves.  
> **Note #2:** As of the time of this writing in late 2017, Docker announced it will support both [Swarm and Kubernetes](https://www.docker.com/kubernetes) as orchestration engines. Some believe that with support for Kubernetes, Docker Swarm will become obsolete. Others say that Swarm will continue to be relevant, as a simpler orchestration tool which is suitable for organizations with smaller container workloads.

Swarm's capabilities include coordination between containers, allocating tasks to groups of containers, health checks and lifecycle management of containers, redundancy and failover, scaling containers up and down based on load, and rolling updates.

Docker Swarm components:

* **Swarm** – a swarm consists of multiple Docker hosts which run in swarm mode and act as managers and workers.
Task – the swarm manager distributes a specific number of tasks among the nodes, based on the service scale you specify. A task carries a Docker container and the commands to run inside the container. Once a task is assigned to a node, it cannot move to another node. It can only run on the assigned node or fail.

* **Service** – a service is the definition of the tasks to execute on the manager or worker nodes. When you create a service, you specify which container image to use and which commands to execute inside running containers. 

* **Nodes** – a swarm node is an individual Docker Engine participating in the swarm. You can run one or more nodes on a single physical computer or cloud server, but production swarm deployments typically include Docker nodes distributed across multiple machines.

* **Manager nodes** – dispatch units of work called tasks to worker nodes. Manager nodes also perform orchestration and cluster management functions.

* **Leader node** – manager nodes elect a single leader to conduct orchestration tasks, using the Raft consensus algorithm.

* **Worker nodes** – receive and execute tasks dispatched from manager nodes. By default manager nodes also run services as worker nodes. An agent runs on each worker node and reports on the tasks assigned to it to its manager node.

* **Load balancing** – the swarm manager uses ingress load balancing to expose the services running on the Docker swarm, enabling external access. 