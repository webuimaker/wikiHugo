---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 4  # Order that this section will appear.
title: "How Containers Communicate with the Outside World"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---

There are different ways in which Docker containers can communicate with the outside world, as detailed below.
## Exposing Ports and Forwarding Traffic
In most cases, Docker networks use subnets without access from the outside world. To allow requests from the Internet to reach the container, you’ll need to map container ports to ports on the container’s host. For example, a request to `hostname:8000` will be forwarded to whatever service is running inside the container on port 80, if a mapping from host port 8000 to container port 80 to was previously defined.



**See Docker Documentation:** {{< read-more "Exposing and publishing ports"  "https://docs.docker.com/engine/userguide/networking/#exposing-and-publishing-ports" "_blank"  >}}

## Containers Connected to Multiple Networks

Fine-grained network policies for connectivity and isolation can be achieved by joining containers to multiple networks. By default each container will be attached to a single network. More networks can be attached to a container by creating it first with `docker create` (instead of `docker run`) and then running the command `docker network connect`. For example:

`$ docker network create net1 # creates bridge network name net1
$ docker network create net2 # creates bridge network name net2
$ docker create -it --net net1 --name cont1 busybox sh # creates container named cont1 attached to network net1
$ docker network connect net2 cont1 # further attaches container cont1 to network net2`


The container is now connected to two distinct networks simultaneously.


**See Docker Documentation:** {{< read-more "User-defined networks"  "https://docs.docker.com/engine/userguide/networking/#user-defined-networks" "_blank"  >}}


## How IPv6 Works on Docker

By default, Docker configures the container networks for IPv4 only. To enable IPv4/IPv6 dual stack the `--ipv6` flag needs to be applied when starting the Docker daemon. Then the `docker0` bridge will get an IPv6 link-local address `fe80::1`. To assign globally routable IPv6 addresses to your containers, use the flag `--fixed-cidr-v6` followed by ipv6 address.

**See Docker Documentation:** {{< read-more "IPv6 with Docker"  "https://docs.docker.com/engine/userguide/networking/default_network/ipv6/" "_blank"  >}}

