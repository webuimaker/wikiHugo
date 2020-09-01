---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 1  # Order that this section will appear.
title: "What is Docker Networking"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"

---

Since a [Kubernetes cluster](/display/containers/kubernetes+cluster) consists of various nodes and pods, understanding how they communicate between them is essential. The Kubernetes networking model supports different types of open source implementations. Kubernetes provides an IP address to each pod so that there is no need to map host ports to container ports as in the Docker networking model. Pods behave much like VMs or physical hosts with respect to port allocation, naming, load balancing and application configuration.  For more background on Kubernetes components, see [Kuberenetes Architecture](/display/containers/kubernetes+architecture+101).

**For further reading, see Kubernetes Documentation:** {{< read-more "Cluster Networking - Summary" "https://kubernetes.io/docs/concepts/cluster-administration/networking/#summary" "_blank"  >}}