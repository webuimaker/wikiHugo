---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 6  # Order that this section will appear.
title: "7.KUBERNETES NETWORKING"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"

---

Since a Kubernetes cluster consists of various nodes and pods, understanding how they communicate between them is essential. The Kubernetes networking model supports different types of open source implementations. Kubernetes provides an IP address to each pod so that there is no need to map host ports to container ports as in the Docker networking model. Pods behave much like VMs or physical hosts with respect to port allocation, naming, load balancing and application configuration.

## Kubernetes vs Docker Networking Model

The Docker networking model relies, by default, on a virtual bridge network called Docker0. It is a per-host private network where containers get attached (and thus can reach each other) and allocated a private IP address. This means containers running on different machines are not able to communicate with each other (as they are attached to different hosts’ networks). In order to communicate across nodes with Docker, we have to map host ports to container ports and proxy the traffic. In this scenario, it’s up to the Docker operator to avoid port clashes between containers.

The Kubernetes networking model, on the other hand, natively supports multi-host networking in which pods are able to communicate with each other by default, regardless of which host they live in. Kubernetes does not provide an implementation of this model by default, rather it relies on third-party tools that comply with the following requirements: all containers are able to communicate with each other without NAT; nodes are able to communicate with containers without NAT; and a container’s IP address is the same from inside and outside the container.

## How Pods Communicate with Each Other

Because each pod has a unique IP in a flat address space inside the Kubernetes cluster, direct pod-to-pod communication is possible without requiring any kind of proxy or address translation. This also allows using standard ports for most applications as there is no need to route traffic from a host port to a container port, as in Docker. Note that because all containers in a pod share the same IP address, container-private ports are not possible (containers can access each other’s ports via localhost:<port>) and port conflicts are possible. However, the typical use case for a pod is to run a single application service (in a similar fashion to a VM), in which case port conflicts are a rare situation.

## How Pods Communicate with Services

Kubernetes services allow grouping pods under a common access policy (e.g. load-balanced). The service gets assigned a virtual IP which pods outside the service can communicate with. Those requests are then transparently proxied (via the kube-proxy component that runs on each node) to the pods inside the service. Different proxy-modes are supported:

*   **iptables:** kube-proxy installs iptables rules trap access to service IP addresses and redirect them to the correct pods.
*   **userspace:** kube-proxy opens a port (randomly chosen) on the local node. Requests on this “proxy port” get proxied to one of the service’s pods (as retrieved from Endpoints API).
*   **ipvs** (from Kubernetes 1.9): calls netlink interface to create ipvs rules and regularly synchronizes them with the Endpoints API.

## Incoming Traffic from the Outside World

Nodes inside a Kubernetes cluster are firewalled from the Internet by default, thus services IP addresses are only targetable within the cluster network. In order to allow incoming traffic from outside the cluster, a service specification can map the service to one or more ```externalIPs``` (external to the cluster). Requests arriving at an external IP address get routed by the underlying cloud provider to a node in the cluster (usually via a load balancer outside Kubernetes). The node then knows which service is mapped to the external IP and also which pods are part of the service, thus routing the request to an appropriate pod.

A minimal ingress specification might look like this:

```java
apiVersion: extensions/v1beta1kind: Ingressmetadata:  name: my-ingressspec:  backend:    serviceName: my-service    servicePort: 80
```

## DNS for Services and Pods

Kubernetes provides its own DNS service to resolve domain names inside the cluster in order for pods to communicate with each other. This is implemented by deploying a regular [Kubernetes service](/display/containers/Kubernetes+Services+101) which does name resolution inside the cluster, and configuring individual containers to contact the DNS service to resolve domain names. Note that this “internal DNS” is compatible and expected to run along with the cloud provider’s DNS service.

Every service gets assigned a DNS name which resolves to the cluster IP of the service. The naming convention includes the service name and its namespace. For example:

```java
my-service.my-namespace.svc.cluster.local
```

## Network Policies 

By default pods can accept traffic from any pod in the cluster. Network policies can restrict how groups of pods are allowed to communicate between them and other network endpoints. A network policy specification uses labels to select pods and define a set of rules which govern what traffic is allowed to and from those pods.

For example:

```java
apiVersion: networking.k8s.io/v1kind: NetworkPolicymetadata:  name: my-network-policy  namespace: defaultspec:  podSelector:    matchLabels:      role: db  policyTypes:  - Ingress  - Egress  ingress:  - from:    - ipBlock:        cidr: 172.17.0.0/16        except:        - 172.17.1.0/24    - namespaceSelector:        matchLabels:          project: my-project    - podSelector:        matchLabels:          role: frontend    ports:    - protocol: TCP      port: 6379  egress:  - to:    - ipBlock:        cidr: 10.0.0.0/24    ports:    - protocol: TCP      port: 5978
```

**Learn more about** {{< read-more "Kubernetes Networking" "/display/containers/kubernetes+networking" >}}

