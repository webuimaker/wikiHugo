---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 12  # Order that this section will appear.
title: "DOCKER NETWORKING..."
titleColor: 
subtitle: ""
sectionHeadingID: "dockercontainers-dockernetworking"
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"

---



## What is [Docker Networking](/display/containers/docker+networking+101)

For [Docker containers](/display/containers/docker+containers) to communicate with each other and the outside world via the host machine, there has to be a layer of networking involved. Docker supports different types of networks, each fit for certain use cases.

For example, building an application which runs on a single Docker container will have a different network setup as compared to a web application with a cluster with database, application and load balancers which span multiple containers that need to communicate with each other. Additionally, clients from the outside world will need to access the web application container.

See Docker Documentation:   {{< read-more "Network containers" "https://docs.docker.com/engine/tutorials/networkingcontainers"  "_target"  >}}

## Docker Default Networking (docker0)

When Docker is installed, a default bridge network named  `docker0` is created. Each new Docker container is automatically attached to this network, unless a custom network is specified.

Besides  `docker0`  , two other networks get created automatically by Docker:  `host`  (no isolation between host and containers on this network, to the outside world they are on the same network) and  `none` (attached containers run on container-specific network stack).

See Docker Documentation:  {{< read-more "Default networks" "https://docs.docker.com/engine/userguide/networking/#default-networks" "_target"  >}}

## Network Types

Docker comes with network drivers geared towards different use cases. The most common network types being:  **bridge**  ,  **overlay**  , and  **macvlan**  .

## Bridge Networks

Bridge networking is the most common network type. It is limited to containers within a single host running the Docker engine. Bridge networks are easy to create, manage and troubleshoot.

For the containers on bridge network to communicate or be reachable from the outside world, port mapping needs to be configured. As an example, consider you can have a Docker container running a web service on port   **80**. Because this container is attached to the bridge network on a private subnet, a port on the host system like **8000**  needs to be mapped to port  80 on the container for outside traffic to reach the web service. 

To create a bridge network named  `my-bridge-net`  , pass the argument  `bridge`  to the  `-d`  (driver) parameter as shown below:

```
$ docker network create -d bridge my-bridge-net
```

See Docker Documentation:    {{< read-more "Bridge networks"  "https://docs.docker.com/engine/userguide/networking/#bridge-networks" "_target"  >}}

## Overlay Networks

An overlay network uses software virtualization to create additional layers of network abstraction running on top of a physical network. In Docker, an overlay network driver is used for multi-host network communication. This driver utilizes Virtual Extensible LAN (VXLAN) technology which provide portability between cloud, on-premise and virtual environments. VXLAN solves common portability limitations by extending layer 2 subnets across layer 3 network boundaries, hence containers can run on foreign IP subnets.

To create an overlay network named `my-overlay-net`, you’ll also need the `--subnet` parameter to specify the network block that Docker will use to assign IP addresses to the containers:

```
$ docker network create -d overlay --subnet=192.168.10.0/24 my-overlay-net
```

See Docker Documentation:    {{< read-more "An overlay network without swarm mode"  "https://docs.docker.com/engine/userguide/networking/#an-overlay-network-without-swarm-mode" "_target"  >}}

## Macvlan Networks

The macvlan driver is used to connect Docker containers directly to the host network interfaces through layer 2 segmentation. No use of port mapping or network address translation (NAT) is needed and containers can be assigned a public IP address which is accessible from the outside world. Latency in macvlan networks is low since packets are routed directly from Docker host network interface controller (NIC) to the containers.

Note that macvlan has to be configured per host, and has support for physical NIC, sub-interface, network bonded interfaces and even teamed interfaces. Traffic is explicitly filtered by the host kernel modules for isolation and security. To create a macvlan network named `macvlan-net`, you’ll need to provide a `--gateway` parameter to specify the IP address of the gateway for the subnet, and a `-o` parameter to set driver specific options. In this example, the `parent` interface is set to `eth0` interface on the host:

```
$ docker network create -d macvlan \
  --subnet=192.168.40.0/24 \
  --gateway=192.168.40.1 \
  -o parent=eth0 my-macvlan-net
```

See Docker Documentation: {{< read-more "Get started with Macvlan network driver"  "https://docs.docker.com/engine/userguide/networking/get-started-macvlan/" "_target"  >}}

## How Containers Communicate with Each Other

Different networks provide different communication patterns (for example by IP address only, or by container name) between containers depending on network type and whether it’s a Docker default or a user-defined network.

## Container discovery on docker0 network (DNS resolution)

Docker will assign a name and hostname to each container created on the default `docker0` network, unless a different name/hostname is specified by the user. Docker then keeps a mapping of each name/hostname against the container’s IP address. This mapping allows pinging each container by name as opposed to IP address.

Furthermore, consider the following example which starts a Docker container with a custom name, hostname and DNS server:

```
$ docker run --name test-container -it \
--hostname=test-con.example.com \
--dns=8.8.8.8 \
ubuntu /bin/bash
```

In this example, processes running inside `test-container`, when confronted with a hostname not in `/etc/hosts`, will connect to address 8.8.8.8 on port 53 expecting a DNS service.

See Docker Documentation: {{< read-more "Embedded DNS server in user-defined networks"  "https://docs.docker.com/engine/userguide/networking/configure-dns/" "_target" >}}

## Directly linking containers

It is possible to directly link one container to another using the `--link` option when starting a container. This allow containers to discover each other and securely transfer information about one container to another container. However, Docker has deprecated this feature and recommends creating user-defined networks instead.

As an example, imagine you have a `mydb` container running a database service. We can then create an application container named `myweb` and directly link it to `mydb`:

```
$ docker run --name myweb --link mydb:mydb -d -P myapp python app.py

```

For further reading see Docker Documentation:  {{< read-more "Legacy container links"  "https://docs.docker.com/engine/userguide/networking/default_network/dockerlinks/" "_target"  >}}

## How Containers Communicate with the Outside World

There are different ways in which Docker containers can communicate with the outside world, as detailed below.

## Exposing Ports and Forwarding Traffic

In most cases, Docker networks use subnets without access from the outside world. To allow requests from the Internet to reach the container, you’ll need to map container ports to ports on the container’s host. For example, a request to `hostname:8000` will be forwarded to whatever service is running inside the container on port 80, if a mapping from host port 8000 to container port 80 to was previously defined.

See Docker Documentation:   {{< read-more "Exposing and publishing ports"  "https://docs.docker.com/engine/userguide/networking/#exposing-and-publishing-ports"  "_target"  >}}

## Containers Connected to Multiple Networks

Fine-grained network policies for connectivity and isolation can be achieved by joining containers to multiple networks. By default each container will be attached to a single network. More networks can be attached to a container by creating it first with `docker create` (instead of `docker run`) and then running the command `docker network connect`. For example:

```
$ docker network create net1 # creates bridge network name net1
$ docker network create net2 # creates bridge network name net2
$ docker create -it --net net1 --name cont1 busybox sh # creates container named cont1 attached to network net1
$ docker network connect net2 cont1 # further attaches container cont1 to network net2
```

The container is now connected to two distinct networks simultaneously.

See Docker Documentation:    {{< read-more "User-defined networks"  "https://docs.docker.com/engine/userguide/networking/#user-defined-networks" "_target"  >}}

## How IPv6 Works on Docker

By default, Docker configures the container networks for IPv4 only. To enable IPv4/IPv6 dual stack the `--ipv6` flag needs to be applied when starting the Docker daemon. Then the `docker0` bridge will get an IPv6 link-local address `fe80::1`. To assign globally routable IPv6 addresses to your containers, use the flag `--fixed-cidr-v6` followed by ipv6 address.

See Docker Documentation:  {{< read-more "IPv6 with Docker"  "https://docs.docker.com/engine/userguide/networking/default_network/ipv6/" "_target"  >}}

## Common Operations

Some common operations with Docker networking include:

- **Inspect a network:** To see a specific network’s configuration details like subnet information, network name, IPAM driver, network ID, network driver, or connected containers, use the `docker network inspect` command.
- **List all networks:** Run `docker network ls` to display all networks (along with their type and scope) present on the current host.
- **Create a new network:** To create a new network, use the `docker network create` command and specify if it's of type bridge (default), overlay or macvlan.
- **Run or connect a container to a specific network:** Note first of all, the network must exist already on the host. Either specify the network at container creation/startup time (`docker create` or `docker run`) with the `--net` option; or attach an existing container by using the `docker network connect` command. For example: 
``` docker network connect my-network my-container
```
- **Disconnect a container from a network:** The container must be running to disconnect it from the network using the `docker network disconnect` command.
- **Remove an existing network:** A network can only be removed using the command `docker network rm` if there are no containers attached to it. When a network is removed, the associated bridge will be removed as well.

## Docker Networking with Multiple Hosts

When working with multi-host, there is a need to use higher-level Docker orchestration tools to ease management of networking between a cluster of machines. Popular orchestration tools today include Docker Swarm, Kubernetes, and Apache Mesos.

## Docker Swarm

[Docker Swarm](/display/containers/docker+swarm+101) is a Docker Inc. native tool used to orchestrate Docker containers. It enables you to manage a cluster of hosts as a single resource pool.

Docker Swarm makes use of overlay networks for inter-host communication. The swarm manager service is responsible for automatically assigning IP addresses to the containers.

For service discovery, each service in the swarm gets assigned a unique DNS name. Additionally, Docker Swarm has an embedded DNS server. You can query every container running in the swarm through this embedded DNS server.

See Docker Documentation:  {{< read-more "Manage swarm service networks"  "https://docs.docker.com/engine/swarm/networking/"  "_target"  >}}

## Kubernetes

[Kubernetes Guide](/display/containers/kubernetes+guide) is a system used for automating deployment, scaling, and management of containerized applications, either on a single host or across a cluster of hosts.
  
Kubernetes approaches networking in a different way as compared to Docker, using native concepts like services and pods. Each pod has an IP address and no linking of pods is required, neither do you need to explicitly map container ports to host ports. There are DNS-based service discovery plugins which can be used for service discovery.


Apache Mesos

Apache Mesos is an open-source project used to manage a cluster of containers, providing efficient resource sharing and isolation across distributed applications.

Mesos uses IP address management (IPAM) server and client to manage containers networking. The role of the IPAM server is to assign IP addresses on demand while the IPAM client acts as a bridge between a network isolator module and the IPAM server. A network isolator module is a lightweight module that’s loaded into the Mesos agent. It looks at scheduler task requirements and uses IPAM and network isolator services to provide IP addresses to the containers.

Mesos-dns is a DNS-based service discovery for Mesos. It allows applications and services running on Mesos to find each other through the DNS service.

Read more on this wiki:  {{< read-more "Docker Networking 101"  "/display/containers/docker+networking+101"   >}}






















