---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 5  # Order that this section will appear.
title: "Common Operations"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---

Some common operations with Docker networking include:

<strong>Inspect a network: </strong>To see a specific network’s configuration details like subnet information, network name, IPAM driver, network ID, network driver, or connected containers, use the `docker network inspect` command.

<strong>List all networks:</strong> Run `docker network ls` to display all networks (along with their type and scope) present on the current host.

<strong>Create a new network: </strong>To create a new network, use the `docker network create` command and specify if it's of type bridge (default), overlay or macvlan.

<strong>Run or connect a container to a specific network:</strong> Note first of all, the network must exist already on the host. Either specify the network at container creation/startup time (`docker create` or `docker run`) with the `--net` option; or attach an existing container by using the `docker network connect` command. For example:

`docker network connect my-network my-container`

<strong>Disconnect a container from a network: </strong>The container must be running to disconnect it from the network using the `docker network disconnect` command.

<strong>Remove an existing network:</strong> A network can only be removed using the command `docker network rm` if there are no containers attached to it. When a network is removed, the associated bridge will be removed as well.


