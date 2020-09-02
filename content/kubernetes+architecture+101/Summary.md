---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 10  # Order that this section will appear.
title: "Summary"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
Kubernetes is an orchestration tool for managing distributed services or containerized applications across a distributed cluster of nodes. It was designed for natively supporting (auto-)scaling, high availability, security and portability. Kubernetes itself follows a client-server architecture, with a master node composed of etcd cluster, kube-apiserver, kube-controller-manager, cloud-controller-manager, scheduler. Client (worker) nodes are composed of kube-proxy and kubelet components. Core concepts in Kubernetes include pods (a group of containers deployed together), services (a group of logical pods with a stable IP address) and deployments (a definition of the desired state for a pod or replica set, acted upon by a controller if the current state differs from the desired state), among others.