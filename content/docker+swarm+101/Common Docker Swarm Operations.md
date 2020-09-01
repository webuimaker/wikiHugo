---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 5  # Order that this section will appear.
title: "Common Docker Swarm Operations"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---


In this section you will learn:

* [How to create a swarm](#DockerSwarm101-create-swarm)

* [How to add and manage nodes in a swarm](#DockerSwarm101-manage-nodes)

* [How to deploy services to a swarm](#DockerSwarm101-deploy)
 
* [Swarm admin commands](#DockerSwarm101-admin)
## Creating and Joining a Swarm 

The Docker engine runs with swarm mode disabled by default. To run Docker in swarm mode, you can either create a new swarm or have the container join an existing swarm. 

<strong>To create a swarm </strong>– run the `docker swarm init` command, which creates a single-node swarm on the current Docker engine. The current node becomes the manager node for the newly created swarm.

<strong>To join a swarm </strong>– the output for the docker swarm init command tells you which command you need to run on other Docker containers to allow them to join your swarm as worker nodes, including a “join token”. For example, to add a worker to this swarm, run the following command:

`docker swarm join \
--token SWMTKN-1-49nj1cmql0jkz5s954yi3oex3nedyz0fb0xx14ie39trti4wxv-8vxv8rssmk743ojnwacrr2e7c \
192.168.99.100:2377`

There is a different join token for worker nodes and manager nodes. The token is only used at the time a container joins the swarm. Manager tokens should be strongly protected, because any access to the manager token grants control over an entire swarm. 

You can run `swarm join-token --rotate` at any time to invalidate the older token and generate a new one, for security purposes.

<strong>Accessing management functionality </strong>– swarm nodes can access the SwarmKit API (providing operations like node discovery and task scheduling) and overlay networking, using an “advertise address” you specify for the manager node. If you don’t specify an address, and there is a single IP for the system, Docker listens by default on port 2377. SwarmKit is a toolkit for orchestrating distributed systems, including node discovery and task scheduling. 

 
**For more details, see the Swarm documentation:** {{< read-more "Create a Swarm"  "https://docs.docker.com/engine/swarm/swarm-tutorial/create-swarm/" "_blank"  >}}


## Manage Nodes in a Swarm 
To get visibility into the nodes on your swarm, list them using the docker node ls command on a manager node. 

The listed nodes display an availability status that identifies whether the scheduler can assign tasks to the node. 

* A <strong> manager status</strong> value identifies whether the node participates in swarm management.

* A blank value indicates that the node is a worker node. 

* A `Leader` value identifies the primary manager node that makes all swarm management and orchestration decisions for the swarm. 

* A `Reachable` value identifies nodes that are manager nodes and are candidates to become leader nodes in the event that a leader node is unavailable.

* An `Unavailable` value signifies a manager node that cannot communicate with other managers. Such nodes should be replaced by promoting worker nodes or adding a new manager node. 

**For more details, see the Swarm Documentation:** {{< read-more "Manage Nodes in a Swarm"  "https://docs.docker.com/engine/swarm/manage-nodes/" "_blank"  >}}


## Deploying Services to a Swarm 
After you declare the desired state for a service you want to run in your cluster, you rely on Docker Swarm to maintain that state. 

<strong>To create a service</strong>, use the `docker service create` command and name it with a `--name` flag. After the `--name` flag comes the container image name that you want to use. You can also specify a command for the service's containers to run. 

The command below starts a service called  `my_web`  which uses an  `nginx`  image and runs the command  `ping docker.com` :

`$ docker service create --name my_web nginx ping docker.com`

<strong>To remove a service</strong>, use the `docker service remove` command. You can remove a service by its ID or name, as shown in the output of the docker service ls command. The following command removes the  `my_web`  service:

`$ docker service remove my_web`

<strong>To update service configuration</strong>, use the `docker service update` command. This lets you configure settings for a service after it is created, including publishing ports to clients outside the swarm, resource constraints, and whether the service should start automatically when Docker starts. 

The following is a list of some of the configuration options you can specify for a service: 

* Configure runtime environment
* Update the command an existing service runs
* Specify the image version a service should use
* Publish ports
* Connect the service to an overlay network
* Control service scale and placement
* Reserve memory or CPUs for a service
* Configure a service’s update behavior
* Automatically roll back if an update fails

**For more details, see the Swarm documentation:** {{< read-more "Deploying Services to a Swarm"  "https://docs.docker.com/engine/swarm/services/" "_blank"  >}}


## Admin Commands 
Docker uses the Raft Consensus Algorithm to manage swarms. Raft requires a majority of manager nodes (quorum) to agree on proposed updates to the swarm, such as node additions or removals. 

For <strong>fault tolerance</strong> in the Raft algorithm, you should always maintain an odd number of managers in the swarm to better support manager node failures. Having an odd number of managers results in a higher chance that a quorum remains available to process requests, if the network is partitioned into two sets.

You can <strong>monitor node health</strong> using the `docker node ls` command from a manager node or querying the nodes with the command line `operation docker node inspect <id-node>.` 

You can <strong>forcibly remove a node </strong>from a swarm without shutting it down first, by using the `docker node rm` command and a `--force` flag. This might be needed if a node becomes compromised. Here is what this looks like:

`$ docker node rm --force node9Node node9 removed from swarm`


 You can <strong>backup a swarm</strong> using any manager node, as follows: 

1. You’ll need an unlock key, if auto-lock is enabled on the swarm.

2. Terminate Docker on the manager node before backing up data—this ensures no data changes in the manager node during the backup operation.

3. Backup the entire /var/lib/docker/swarm/ directory, which stores the swarm state and the manager logs.

4. Restart the manager node.

**For more details and additional admin functions, see the Swarm Documentation:** {{< read-more "Swarm Administration Guide"  "https://docs.docker.com/engine/swarm/admin_guide/" "_blank"  >}}
