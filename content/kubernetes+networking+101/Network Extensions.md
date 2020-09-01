---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 9  # Order that this section will appear.
title: "Network Extensions"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---


Network extensions are the way to extend or enhance the networking by introducing various network functionalities such as cross-node networking or network policies. There are two types of network extensions or plugins:

*   **CNI plugin**: designed for interoperability, this plugin implements the  [Container Network Interface (CNI) specification](https://github.com/containernetworking/cni/blob/master/SPEC.md)  inserting a network interface into the container network namespace (e.g. one end of a veth pair) and making any necessary changes on the host (for example, attaching the other end of the veth into a bridge). 
*   **Kubenet plugin** : a simple plugin for Linux usage only, typically used together with a cloud provider that sets up routing rules for communication between nodes.

**For further reading, see Kubernetes documentation:** {{< read-more "Network Plugins"  "https://kubernetes.io/docs/concepts/cluster-administration/network-plugins/" >}}
