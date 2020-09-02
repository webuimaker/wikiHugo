---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 2  # Order that this section will appear.
title: "Service Types Comparison ClusterIP vs NodePort vs LoadBalancer vs Ingress"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---



NodePorts, LoadBalancers, and Ingress are different ways to get external traffic into a Kubernetes cluster. Below we explain the differences between these types of services.

<strong>ClusterIP</strong>

A ClusterIP service is the default type of service in Kubernetes. It creates a service inside the Kubernetes cluster, which can be accessed by other applications in the cluster, without allowing external access.

A ClusterIP exposes the following:

`spec.clusterIp:spec.ports[*].port`


<strong>NodePort</strong>

A NodePort service opens a specific port on all the Nodes in the cluster, and any traffic sent to that port is forwarded to the service. The service cannot be accessed from the cluster IP. 

A NodePort exposes the following:

```
<NodeIP>:spec.ports[*].nodePort
spec.clusterIp:spec.ports[*].port
``` 

<strong>LoadBalancer</strong>

A LoadBalancer is a standard way to expose a Kubernetes service externally so it can be accessed over the internet. If you are using Google Kubernetes Engine (GKE), this creates a Network Load Balancer with one IP address, which external users can access and are then forwarded to the relevant node in your Kubernetes cluster. A LoadBalancer can also be accessed in the same way as a ClusterIP or NodePort

A LoadBalancer exposes the following:

```
spec.loadBalancerIp:spec.ports[*].port
<NodeIP>:spec.ports[*].nodePort
spec.clusterIp:spec.ports[*].port

```

<strong>Ingress</strong>

Ingress is actually not a type of service. It sits in front of multiple services and performs smart routing between them, providing access to your cluster. There are several types of ingress controllers that have different routing capabilities. In GKE, the ingress controller creates an HTTP Load Balancer, which can route traffic to services in the Kubernetes cluster based on path or subdomain.