---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 1  # Order that this section will appear.
title: "What is Kubernetes"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"

---

Kubernetes is a container orchestration system, which can be used to manage large numbers of containers on top of physical infrastructure. Kubernetes was built by Google based on their experience running massive amount of containers in production.

It's important to understand that unlike the popular [Docker](/display/containers/docker+containers) Engine, Kubernetes is not a container engine. It is a system that helps you manage containers. Typically Kubernetes deployments use Docker as the underlying container engine, but can also be used with other container engines [such as rkt](https://coreos.com/rkt/).

The diagram below shows the [Kubernetes architecture](/display/containers/kubernetes+architecture+101). In Kubernetes, the master node places container workloads in user pods, on worker nodes or on the master node itself. 

Additional Kubernetes components include:

* <strong>etcd:</strong> Stores configuration data, for access by the Kubernetes Master’s API Server.

* <strong>API Server:</strong> The management hub for the Kubernetes master node, allowing communication between other components.

* <strong>ontroller Manager:</strong> Scales workloads up and down to ensure the cluster reaches its desired state.

* <strong>Scheduler:</strong> This component places the workload on the appropriate node – in this case all workloads will be placed locally on your host.

* <strong>Kubelet:</strong> Receives pod specifications from the API Server and manages running pods.

* <strong>Pods:</strong> Kubernetes deploys and schedules containers in groups called pods. All the containers in a single pod run on the same node, and share resources on the physical host.

Important Kubernetes concepts:

* <strong>Deployments:</strong> Used to create and manage a group of pods. Kubernetes supports service deployments, which enable scaling across multiple nodes.

* <strong>Services:</strong> Endpoints that can be connected to pods using label selectors. A service round-robins requests between pods. Services are the external point of contact for container workloads, accessible via an internal DNS server.
 
* <strong>Labels:</strong> Key-value pairs that can be used to find multiple objects within the Kubernetes cluster and update them in bulk.