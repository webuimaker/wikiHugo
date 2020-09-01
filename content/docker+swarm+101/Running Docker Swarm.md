---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 4  # Order that this section will appear.
title: "Running Docker Swarm"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---

The Docker engine runs with swarm mode disabled by default. To run Docker in swarm mode, you can either create a new swarm or have the container join an existing swarm. 

To create a swarm, run the `docker swarm init` command, which creates a single-node swarm on the current Docker engine. The current node becomes the manager node for the newly created swarm.

The output for the docker swarm init command tells you which command you need to run on other Docker containers to allow them to join your swarm as worker nodes. 

Other nodes can access the SwarmKit API using the manager node's advertised IP address. SwarmKit is a toolkit for orchestrating distributed systems, including node discovery, task scheduling, and more. 

Each node requires a secret token to join a swarm. The token for worker nodes is different from the token for manager nodes, and the token is only used at the time a container joins the swarm. 

Manager tokens should be strongly protected, because any access to the manager token grants control over an entire swarm. 

**For more details, see the Swarm documentation:** {{< read-more "Run Docker in Swarm mode"  "https://docs.docker.com/engine/swarm/swarm-mode/" "_blank"  >}}

