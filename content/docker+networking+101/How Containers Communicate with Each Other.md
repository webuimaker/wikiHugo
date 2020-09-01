---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 3  # Order that this section will appear.
title: "How Containers Communicate with Each Other"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---

The Docker networking model relies, by default, on a virtual bridge network called `Docker0`. It is a per-host private network where containers get attached (and thus can reach each other) and allocated a private IP address. This means containers running on different machines are not able to communicate with each other (as they are attached to different hosts’ networks). In order to communicate across nodes with Docker, we have to map host ports to container ports and proxy the traffic. In this scenario, it’s up to the Docker operator to avoid port clashes between containers.

The Kubernetes networking model, on the other hand, natively supports multi-host networking in which pods are able to communicate with each other by default, regardless of which host they live in. Kubernetes does not provide an implementation of this model by default, rather it relies on third-party tools that comply with the following requirements: all containers are able to communicate with each other without NAT; nodes are able to communicate with containers without NAT; and a container’s IP address is the same from inside and outside the container.


Kubernetes follows an “IP-per-pod” model where each pod get assigned an IP address and all containers in a single pod share the same network namespaces and IP address. Containers in the same pod can therefore reach each other’s ports via `localhost:<port>`. However, it is not recommended to communicate directly with a pod via its IP address due to pod’s volatility (a pod can be killed and replaced at any moment). Instead, use a [Kubernetes service](/display/containers/kubernetes+services+101) which represents a group of pods acting as a single entity to the outside. Services get allocated their own IP address in the cluster and provide a reliable entry point.


See Kubernetes documentation: Cluster Networking - Kubernetes Model



**For further reading, see Kubernetes Documentation:** {{< read-more "Cluster Networking - Kubernetes Model" "https://kubernetes.io/docs/concepts/cluster-administration/networking/#kubernetes-model" "_target"  >}}
