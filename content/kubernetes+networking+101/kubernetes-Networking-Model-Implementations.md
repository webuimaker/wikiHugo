---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 3  # Order that this section will appear.
title: "Kubernetes Networking Model Implementations"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---

Kubernetes does not provide a default network implementation, it only enforces a model for third-party tools to implement. There is a variety of implementations nowadays, below we list some popular ones.

*   **[Flannel](https://github.com/coreos/flannel#flannel)** -  a very simple overlay network that satisfies the Kubernetes requirements. Flannel runs an agent on each host and allocates a subnet lease to each of them out of a larger, preconfigured address space.   
     Flannel creates a flat network called as overlay network which runs above the host network. 
*   **[Project Calico](https://docs.projectcalico.org/v3.0/introduction/)** - an open source container networking provider and network policy engine. Calico provides a highly scalable networking and network policy solution for connecting Kubernetes pods based on the same IP networking principles as the internet. Calico can be deployed without encapsulation or overlays to provide high-performance, high-scale data center networking.
*   **[Weave Net](https://www.weave.works/oss/net/)** - a cloud native networking toolkit which provides a resilient and simple to use (does not require any configuration) network for Kubernetes and its hosted applications. It provides various functionalities like scaling, service discovery, performance without complexity and secure networking.

**For further reading, see Kubernetes Documentation:** {{< read-more "Cluster Networking - How to achieve this" "https://kubernetes.io/docs/concepts/cluster-administration/networking/#how-to-achieve-this" "_blank"  >}}
