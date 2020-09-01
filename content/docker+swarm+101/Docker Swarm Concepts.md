---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 2  # Order that this section will appear.
title: "Docker Swarm Concepts"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---

<strong>Swarmkit</strong>&nbsp;– a separate project which implements Docker’s orchestration layer and is used directly within Docker to implement Docker swarm mode.

<strong>Swarm</strong>&nbsp;– a swarm consists of multiple Docker hosts which run in swarm mode and act as managers and workers.


<strong>Task</strong>&nbsp;– the swarm manager distributes a specific number of tasks among the nodes, based on the service scale you specify. A task carries a Docker container and the commands to run inside the container. Once a task is assigned to a node, it cannot move to another node. It can only run on the assigned node or fail.

<strong>Service</strong>&nbsp;– a service is the definition of the tasks to execute on the manager or worker nodes. When you create a service, you specify which container image to use and which commands to execute inside running containers. A key difference between services and standalone containers is that you can modify a service’s configuration, including the networks and volumes it is connected to, without manually restarting the service.

<strong>Nodes</strong>&nbsp;– a swarm node is an individual Docker Engine participating in the swarm. You can run one or more nodes on a single physical computer or cloud server, but production swarm deployments typically include Docker nodes distributed across multiple machines.

<strong>Manager nodes</strong>&nbsp;– dispatches units of work called tasks to worker nodes. Manager nodes also perform orchestration and cluster management functions.

<strong>Leader node</strong>&nbsp;– manager nodes elect a single leader to conduct orchestration tasks, using the Raft consensus algorithm.

<strong>Worker nodes</strong>&nbsp;– receive and execute tasks dispatched from manager nodes. By default manager nodes also run services as worker nodes. An agent runs on each worker node and reports on the tasks assigned to it to its manager node.

<strong>Load balancing</strong>&nbsp;– the swarm manager uses ingress load balancing to expose the services running on the Docker swarm, enabling external access. The swarm manager assigns a configurable PublishedPort for the service. External components, such as cloud load balancers, can access the service on the PublishedPort of any node in the cluster, whether or not the node is currently running the task for the service. All nodes in the swarm route ingress connections to a running task instance. The swarm manager uses internal load balancing to distribute requests among services within the cluster based upon the DNS name of the service.


