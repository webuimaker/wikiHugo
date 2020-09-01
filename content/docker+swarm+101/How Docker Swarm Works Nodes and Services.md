---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 3  # Order that this section will appear.
title: "How Docker Swarm Works Nodes and Services"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
## How Nodes Work

There are two types of nodes: managers and workers. 

<strong>Manager nodes</strong>  handle cluster management tasks: maintaining cluster state, scheduling services, and serving swarm mode HTTP API endpoints. The managers maintain a consistent state of the swarm and services running on it, using an implementation of the Raft algorithm.

Running multiple manager nodes allows you to take advantage of swarm mode’s fault-tolerance features. However, adding more managers does not mean increased scalability or higher performance. In general, the opposite is true. Docker recommends implementing an odd number of manager nodes. 

A three-manager swarm tolerates a maximum loss of one manager without downtime. A five-manager swarm tolerates a maximum simultaneous loss of two manager nodes. In general, an N manager cluster will tolerate the loss of at most (N-1)/2 managers. When managers fail beyond this threshold, services continue to run, but you need to create a new cluster to recover.

<strong>Worker nodes</strong> are also instances of Docker Engine whose sole purpose is to run containers. Worker nodes require at least one manager node to function. 

By default, all managers are also workers. In a single manager node cluster, you can run commands like `docker service create` and the scheduler places all tasks on the local Engine. To prevent a manager node from executing tasks, set the availability for a manager node to `Drain`. 

You can promote a worker node to be a manager by running docker node promote. For example, you may want to promote a worker node when you take a manager node offline for maintenance. You can also demote a manager node to a worker node using node demote. For more details on node commands in a swarm cluster, see the [Docker node CLI reference](https://docs.docker.com/engine/reference/commandline/node/).


## How Services Work
Services allow you to deploy an application image to a Docker swarm. Examples of services include an HTTP server, a database, or other software that needs to run in a distributed environment. The basic definition of the service includes a container image to run, and commands to execute inside the running containers. 

* <strong>Service options –</strong> when you create a service, you can specify the port to publish for external access, an overlay network for the service to connect to other services in the swarm, CPU and memory restrictions, a rolling update policy, and number of replicas of the image to run in the swarm.


* <strong>Services, scheduling and desired state – </strong>when you deploy the service to the swarm, the service definition is the desired state for the service. For example, the desired state might be running three instances of an HTTP listener, with load balancing between them. The swarm manager schedules a replica task on three Docker Engines in the swarm, each of which runs a container with an HTTP listener. If one of these instances fails, the manager recognizes the desired state is not fulfilled, schedules another replica task, and spawns a new container to bring the number of listeners back to three. 

* <strong>When tasks fail – </strong>if a task in a Docker swarm fails, it is not recovered or restarted. The orchestrator simply removes the container related to the failed tasks, and creates a new task to replace it according to the desired state specified by the service.

* <strong>Pending services –</strong> a service is pending if there aren’t currently nodes available in the cluster to run its tasks. For example, this might happen if all the nodes in the cluster are paused or Drained (defined as manager nodes which may not act as worker nodes). You can also specify constraints on a service, such as minimal memory of 100 GB on a node. If no nodes have this amount of memory, the service will be pending until a node joins the swarm that satisfies the requirement. 

* <strong>Replicated vs. global services – </strong>a replicated service specifies a number of identical tasks you want to run. For example, you decide to deploy an HTTP service with three replicas, each serving the same content. A global service is a service that runs one task on all the nodes in the swarm, with no pre-specified number of tasks/nodes. Each time you add a node to the swarm, the same task is run on it. For example, a typical global service is a monitoring agent or an anti-virus scanner.


