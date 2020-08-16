---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 1  # Order that this section will appear.
title: "1.WHAT IS KUBERNETES?"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"

---


Kubernetes is a powerful open source orchestration tool developed by Google for managing microservices or containerized applications across a distributed cluster of nodes. Kubernetes provides highly resilient infrastructure with zero downtime deployment capabilities, automatic rollback, scaling, and self-healing of containers (which consists of auto-placement, auto-restart, auto-replication , and scaling of containers on the basis of CPU usage).

The main objective of Kubernetes is to hide the  complexity of managing a fleet of containers by providing REST APIs for the required functionalities. Kubernetes is portable in nature, meaning it can run on various public or private cloud platforms such as AWS, Azure, OpenStack, or Apache Mesos. It can also run on bare metal machines.

## Kubernetes Advantages and Use Cases

Kubernetes has become popular due to its roots in Google's unparalleled R&D and operations expertise, and the large community that has grown around it since it was release as an open source product. It is used in a variety of scenarios, from simple ones like running WordPress instances on Kubernetes, to scaling Jenkins machines, to secure deployments with thousands of nodes.

**See more resources about:** {{< read-more "Kubernetes Advantages and Use Cases" "/display/containers/kubernetes+advantages+and+use+cases"  >}}

## Kubernetes Components and Architecture


[Kubernetes architecture](/display/containers/kubernetes+architecture+101) follows a client-server architecture. It’s possible to have a multi-master setup (for high availability), but by default there is a single master server which acts as a controlling node and point of contact. The master server consists of various components including a kube-apiserver, an etcd storage, a kube-controller-manager, a cloud-controller-manager, a kube-scheduler, and a DNS server for [Kubernetes services](/display/containers/kubernetes+as+a+service). Node components include kubelet and kube-proxy on top of Docker.

![kubertes](/images/kubertes.png)

<small>High level Kubernetes architecture showing a cluster with a master and two worker nodes ([image source](https://x-team.com/blog/introduction-kubernetes-architecture))</small>


## Kubernetes Master Components

Below are the main components found on the master node:

*   **[etcd cluster](https://kubernetes.io/docs/tasks/administer-cluster/configure-upgrade-etcd/)**-a simple, distributed key value storage which is used to store the Kubernetes cluster data (such as number of pods, their state, namespace, etc), API objects and service discovery details. It is only accessible from the API server for security reasons. etcd enables notifications to the cluster about configuration changes with the help of watchers. Notifications are API requests on each etcd cluster node to trigger the update of information in the node’s storage.
*   **[kube-apiserver](https://kubernetes.io/docs/reference/generated/kube-apiserver/)**-Kubernetes API server is the central management entity that receives all REST requests for modifications (to pods, services, replication sets/controllers and others), serving as frontend to the cluster. Also, this is the only component that communicates with the etcd cluster, making sure data is stored in etcd and is in agreement with the service details of the deployed pods.

*   **[kube-controller-manager](https://kubernetes.io/docs/reference/generated/kube-controller-manager/)**-runs a number of distinct controller processes in the background (for example, replication controller controls number of replicas in a pod, endpoints controller populates endpoint objects like services and pods, and others) to regulate the shared state of the cluster and perform routine tasks. When a change in a service configuration occurs (for example, replacing the image from which the pods are running, or changing parameters in the configuration yaml file), the controller spots the change and starts working towards the new desired state.
*   **[cloud-controller-manager](https://kubernetes.io/docs/concepts/overview/components/#cloud-controller-manager)**-is responsible for managing controller processes with dependencies on the underlying cloud provider (if applicable). For example, when a controller needs to check if a node was terminated or set up routes, load balancers or volumes in the cloud infrastructure, all that is handled by the cloud-controller-manager.
*   **[kube-scheduler](https://kubernetes.io/docs/reference/generated/kube-scheduler/)**-helps schedule the pods (a co-located group of containers inside which our application processes are running) on the various nodes based on resource utilization. It reads the service’s operational requirements and schedules it on the best fit node. For example, if the application needs 1GB of memory and 2 CPU cores, then the pods for that application will be scheduled on a node with at least those resources. The scheduler runs each time there is a need to schedule pods. The scheduler must know the total resources available as well as resources allocated to existing workloads on each node.

## Node (worker) components

Below are the main components found on a (worker) node:

*   [**kubelet** ](https://kubernetes.io/docs/reference/generated/kubelet/)- the main service on a node, regularly taking in new or modified pod specifications (primarily through the kube-apiserver) and ensuring that pods and their containers are healthy and running in the desired state. This component also reports to the master on the health of the host where it is running.
*   **[kube-proxy](https://kubernetes.io/docs/reference/generated/kube-proxy/)**- a proxy service that runs on each worker node to deal with individual host subnetting and expose services to the external world. It performs request forwarding to the correct pods/containers across the various isolated networks in a cluster.

## Kubectl

**[kubectl](https://kubernetes.io/docs/reference/kubectl/overview/)** is a command line tool that interacts with kube-apiserver and send commands to the master node. Each command is converted into an API call.

**Learn more about** {{< read-more " Kubernetes Architecture" "/display/containers/kubernetes+krchitecture+101"  >}}



