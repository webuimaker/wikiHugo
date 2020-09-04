---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 3  # Order that this section will appear.
title: "Networking"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---


Containerized applications are typically based on the microservices architecture. In these systems, networking plays a key role in performance of the applications.

## Linkerd

Linkerd provides a service mesh to connect microservices to one another. Its goal is to provide a uniform layer of communication.


**Get started with** {{< read-more "Linkerd"  "https://linkerd.io/getting-started/" "_blank"  >}}


## Istio

Istio provides APIs and operates a layer above Linkerd. Together, they provide a powerful and feature-rich networking solution for containerized applications.

**Get started with** {{< read-more "Istio"  "https://istio.io/docs/setup/kubernetes/quick-start.html" "_blank"  >}}

## Weave

Service discovery, load balancing, and security are important criteria for container networking, and Weave brings all this together in a single package. It secures communication over the network using encryption, isolation, and segmentation. It provides a ‘micro DNS’ at each node and helps make service discovery easy.


**Get started with** {{< read-more "Weave"  "https://www.weave.works/" "_blank"  >}}

## Flannel


Flannel is a Layer 3 overlay network for Kubernetes. Flannel is a powerful tool for connecting hosts within Kubernetes by allocating a subnet for each host. In so doing, it controls how traffic flows between the hosts.


**Get started with** {{< read-more "Flannel"  "https://velotio.com/blog/2017/4/11/flannel-a-network-fabric-for-containers" "_blank"  >}}