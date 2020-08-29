---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 11  # Order that this section will appear.
title: "DOCKER SWARM..."
titleColor: 
subtitle: ""
sectionHeadingID: "DockerContainers-DOCKERSWARM"
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"

---



## What is Docker Swarm

[Docker](/display/containers/docker+containers) swarm mode allows you to manage a cluster of Docker Engines, natively within the Docker platform. You can use the Docker CLI to create a swarm, deploy application services to a swarm, and manage swarm behavior.

Docker will shortly support [Kubernetes Guide](/display/containers/kubernetes+Guide) as well as [Docker Swarm](/display/containers/docker+swarm+101), and Docker users will be able to use either Kubernetes or Swarm to orchestrate their container workloads.

Swarm can help developers and IT administrators:

- Coordinate between containers and allocate tasks to groups of containers
- Perform health checks and manage lifecycle of individual containers
- Provide redundancy and failover in case nodes experience failure
- Scale the number of containers up and down depending on load
- Perform rolling updates of software across multiple containers

## Docker Swarm Concepts

- **Swarmkit** – a separate project which implements Docker’s orchestration layer and is used directly within Docker to implement Docker swarm mode.
- **Swarm** – a swarm consists of multiple Docker hosts which run in swarm mode and act as managers and workers.
- **Task** – the swarm manager distributes a specific number of tasks among the nodes, based on the service scale you specify. A task carries a Docker container and the commands to run inside the container. Once a task is assigned to a node, it cannot move to another node. It can only run on the assigned node or fail.
- **Service** – a service is the definition of the tasks to execute on the manager or worker nodes. When you create a service, you specify which container image to use and which commands to execute inside running containers. A key difference between services and standalone containers is that you can modify a service’s configuration, including the networks and volumes it is connected to, without manually restarting the service.
- **Nodes** – a swarm node is an individual Docker Engine participating in the swarm. You can run one or more nodes on a single physical computer or cloud server, but production swarm deployments typically include Docker nodes distributed across multiple machines.
- **Manager nodes** – dispatches units of work called tasks to worker nodes. Manager nodes also perform orchestration and cluster management functions.
- **Leader node** – manager nodes elect a single leader to conduct orchestration tasks, using the Raft consensus algorithm.
- **Worker nodes** – receive and execute tasks dispatched from manager nodes. By default manager nodes also run services as worker nodes. An agent runs on each worker node and reports on the tasks assigned to it to its manager node.
- **Load balancing** – the swarm manager uses ingress load balancing to expose the services running on the Docker swarm, enabling external access. The swarm manager assigns a configurable PublishedPort for the service. External components, such as cloud load balancers, can access the service on the PublishedPort of any node in the cluster, whether or not the node is currently running the task for the service. All nodes in the swarm route ingress connections to a running task instance. The swarm manager uses internal load balancing to distribute requests among services within the cluster based upon the DNS name of the service.

## Running Docker Swarm

The Docker engine runs with swarm mode disabled by default. To [run Docker container](/display/containers/running+docker+containers) in swarm mode, you can either create a new swarm or have the container join an existing swarm.

To create a swarm, run the `docker swarm init` command, which creates a single-node swarm on the current Docker engine. The current node becomes the manager node for the newly created swarm.

The output for the docker swarm init command tells you which command you need to run on other Docker containers to allow them to join your swarm as worker nodes. 

Other nodes can access the SwarmKit API using the manager node's advertised IP address. SwarmKit is a toolkit for orchestrating distributed systems, including node discovery, task scheduling, and more. 

Each node requires a secret token to join a swarm. The token for worker nodes is different from the token for manager nodes, and the token is only used at the time a container joins the swarm.

Manager tokens should be strongly protected, because any access to the manager token grants control over an entire swarm. 

For more details, see the Swarm documentation:  {{< read-more "Run Docker in Swarm mode" "https://docs.docker.com/engine/swarm/swarm-mode/"  "_target" >}}

## Common Docker Swarm Operations

In this section you will learn:

*   [How to create a swarm](#dockerContainers-create-swarm)
*   [How to add and manage nodes in a swarm](#dockerContainers-manage-nodes)
*   [How to deploy services to a swarm](#dockerContainers-deploy)
*   [Swarm admin commands](#dockerContainers-admin)


## Creating and Joining a Swarm 

The Docker engine runs with swarm mode disabled by default. To run Docker in swarm mode, you can either create a new swarm or have the container join an existing swarm. 

**To create a swarm** – run the `docker swarm init` command, which creates a single-node swarm on the current Docker engine. The current node becomes the manager node for the newly created swarm.

**To join a swarm** – the output for the docker swarm init command tells you which command you need to run on other Docker containers to allow them to join your swarm as worker nodes, including a “join token”. For example, to add a worker to this swarm, run the following command:

```
docker swarm join \
--token SWMTKN-1-49nj1cmql0jkz5s954yi3oex3nedyz0fb0xx14ie39trti4wxv-8vxv8rssmk743ojnwacrr2e7c \
192.168.99.100:2377
```

There is a different join token for worker nodes and manager nodes. The token is only used at the time a container joins the swarm. Manager tokens should be strongly protected, because any access to the manager token grants control over an entire swarm. 

You can run `swarm join-token --rotate` at any time to invalidate the older token and generate a new one, for security purposes.


**Accessing management functionality** – swarm nodes can access the SwarmKit API (providing operations like node discovery and task scheduling) and overlay networking, using an “advertise address” you specify for the manager node. If you don’t specify an address, and there is a single IP for the system, Docker listens by default on port 2377\. SwarmKit is a toolkit for orchestrating distributed systems, including node discovery and task scheduling.


For more details, see the Swarm documentation: {{< read-more "Create a Swarm" "https://docs.docker.com/engine/swarm/swarm-tutorial/create-swarm/" "_target"  >}}

## Manage Nodes in a Swarm 

To get visibility into the nodes on your swarm, list them using the docker node ls command on a manager node. 

The listed nodes display an availability status that identifies whether the scheduler can assign tasks to the node. 

*   A **manager status** value identifies whether the node participates in swarm management.
*   A blank value indicates that the node is a worker node. 
*   A `Leader` value identifies the primary manager node that makes all swarm management and orchestration decisions for the swarm. 
*   A `Reachable` value identifies nodes that are manager nodes and are candidates to become leader nodes in the event that a leader node is unavailable.
*   An `Unavailable` value signifies a manager node that cannot communicate with other managers. Such nodes should be replaced by promoting worker nodes or adding a new manager node.

For more details, see the Swarm Documentation:  {{< read-more "Manage Nodes in a Swarm" "https://docs.docker.com/engine/swarm/manage-nodes/" "_target"  >}}
Read more on this wiki:   {{< read-more "Docker Swarm 101" "/display/containers/docker+swarm+101"  >}}


 





















