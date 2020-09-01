---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 2  # Order that this section will appear.
title: "Docker Network Types"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
Docker comes with network drivers geared towards different use cases. The most common network types being:  bridge,  overlay, and  macvlan.

## Bridge Networks




Bridge networking is the most common network type. It is limited to containers within a single host running the Docker engine. Bridge networks are easy to create, manage and troubleshoot.

For the containers on bridge network to communicate or be reachable from the outside world, port mapping needs to be configured. As an example, consider you can have a Docker container running a web service on port  <strong>80</strong>  . Because this container is attached to the bridge network on a private subnet, a port on the host system like  <strong>8000</strong>  needs to be mapped to port  80 on the container for outside traffic to reach the web service.

To create a bridge network named  `my-bridge-net`  , pass the argument  `bridge`  to the  `-d ` (driver) parameter as shown below:

`$ docker network create -d bridge my-bridge-net`

**See Docker Documentation:** {{< read-more "Bridge networks" "https://docs.docker.com/engine/userguide/networking/#bridge-networks" "_target"  >}}



## Overlay Networks

An overlay network uses software [virtualization](/display/containers/Docker+Containers+vs.+Virtual+Machines) to create additional layers of network abstraction running on top of a physical network. In Docker, an overlay network driver is used for multi-host network communication. This driver utilizes Virtual Extensible LAN (VXLAN) technology which provide portability between cloud, on-premise and virtual environments. VXLAN solves common portability limitations by extending layer 2 subnets across layer 3 network boundaries, hence containers can run on foreign IP subnets.

To create an overlay network named `my-overlay-net`, you’ll also need the `--subnet` parameter to specify the network block that Docker will use to assign IP addresses to the containers:

`$ docker network create -d overlay --subnet=192.168.10.0/24 my-overlay-net`


**See Docker Documentation:** {{< read-more "An overlay network without swarm mode" "https://docs.docker.com/engine/userguide/networking/#an-overlay-network-without-swarm-mode" "_target"  >}}

## Macvlan Networks

The macvlan driver is used to connect Docker containers directly to the host network interfaces through layer 2 segmentation. No use of port mapping or network address translation (NAT) is needed and containers can be assigned a public IP address which is accessible from the outside world. Latency in macvlan networks is low since packets are routed directly from Docker host network interface controller (NIC) to the containers.

Note that macvlan has to be configured per host, and has support for physical NIC, sub-interface, network bonded interfaces and even teamed interfaces. Traffic is explicitly filtered by the host kernel modules for isolation and security. To create a macvlan network named `macvlan-net`, you’ll need to provide a `--gateway` parameter to specify the IP address of the gateway for the subnet, and a `-o` parameter to set driver specific options. In this example, the `parent` interface is set to `eth0` interface on the host:

`$ docker network create -d macvlan \

  --subnet=192.168.40.0/24 \
  
   --gateway=192.168.40.1 \
   
   -o parent=eth0 my-macvlan-net`

**See Docker Documentation:** {{< read-more "Get started with Macvlan network driver" "https://docs.docker.com/engine/userguide/networking/get-started-macvlan/" "_target"  >}}




