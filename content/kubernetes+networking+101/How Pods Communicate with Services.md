---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 5  # Order that this section will appear.
title: "How Pods Communicate with Services"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---


[Kubernetes services](/display/containers/kubernetes+services) allow grouping pods under a common access policy (for example, load-balanced). The service gets assigned a virtual IP which pods outside the service can communicate with. Those requests are then transparently proxied (via the  [kube-proxy](https://kubernetes.io/docs/reference/generated/kube-proxy/) component that runs on each node) to the pods inside the service. Different proxy-modes are supported:


*   **`iptables`** : kube-proxy installs iptables rules trap access to service IP addresses and redirect them to the correct pods. 

*   **`userspace`** : kube-proxy opens a port (randomly chosen) on the local node. Requests on this “proxy port” get proxied to one of the service’s pods (as retrieved from Endpoints API). 

*   **`ipvs`**  (from Kubernetes 1.9): calls netlink interface to create ipvs rules and regularly synchronizes them with the Endpoints API. 

Kubernetes also offers an Endpoints API for Kubernetes native applications that is updated whenever the set of pods in a service changes. This allows a pod to retrieve the current endpoints for all pods in a service.


**For further reading, see Kubernetes Documentation:** {{< read-more "Cluster Networking - Summary" "https://kubernetes.io/docs/concepts/cluster-administration/networking/#summary" "_blank"  >}}

