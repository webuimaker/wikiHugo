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

Kubernetes is an open source container orchestration platform developed by Google for managing microservices or containerized applications across a distributed cluster of nodes. Kubernetes is highly resilient and supports zero downtime, rollback, scaling, and self-healing of containers. The main objective of Kubernetes is to hide the complexity of managing a fleet of containers. It can run on bare metal machines or on public or private cloud platforms such as AWS, Azure and OpenStack. [Kubernetes architecture](/display/containers/kubernetes+architecture+101) follows a client-server architecture.



<strong>Main Components of the Kubernetes Master Server</strong>

* **[etcd cluster](https://kubernetes.io/docs/tasks/administer-cluster/configure-upgrade-etcd/)** - a distributed key value storage that stores Kubernetes cluster data
* **[kube-apiserver](https://kubernetes.io/docs/reference/generated/kube-apiserver/)** -the central management entity that receives all REST requests for modifications to cluster elements

* **[kube-controller-manager](https://kubernetes.io/docs/reference/generated/kube-controller-manager)** - runs controller processes like replication controller (sets number of replicas in a pod) and endpoints controller (populates services, pods and other objects)
* **[cloud-controller-manager](https://kubernetes.io/docs/concepts/overview/components/#cloud-controller-manager)** -responsible for managing controller processes with dependencies on the underlying cloud provider
* **[kube-scheduler](https://kubernetes.io/docs/reference/generated/kube-scheduler/)** - helps schedule the pods (a co-located group of containers inside which our application processes are running) on the cluster nodes based on resource utilization



<strong>Main components of the Kubernetes Node (Worker) Server</strong>

* **[kubelet](https://kubernetes.io/docs/reference/generated/kubelet/)** - the main service on a node, taking in new or modified pod specifications from kube-apiserver, and ensuring that pods and containers are healthy and running
* **[kube-proxy](https://kubernetes.io/docs/reference/generated/kube-proxy/)** - runs on each worker node to deal with individual host subnetting and expose services
[kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) is a command line tool that interacts with kube-apiserver and send commands to the master node. Each command is converted into an API call.

![alt](/images/kubertes.png )



<small>High level Kubernetes architecture showing a cluster with a master and two worker nodes (image source)</small>

## Kubernetes Tutorials
Kubernetes is a complex system, and learning step by step is the best way to gain expertise. In this page we're compiled all the valuable Kubernetes tutorials from multiple sources - from the big players like Google, Amazon and Microsoft, to individual bloggers and community members. Tutorials are classified into the following categories:

* **[Kubernetes beginner tutorials](#id-70BestKubernetesTutorials-links)** - basic concepts, installation and deployment

* **[Kubernetes AWS and Azure tutorials](#id-70BestKubernetesTutorials-awsazure)** - showing deployment on the popular public clouds, including kops, an official Kubernetes project that can help deploy production-grade clusters on AWS

* **[Kubernetes Vagrant tutorials](#id-70BestKubernetesTutorials-vagrant)** - deploying Kubernetes using Vagrant, a tool for provisioning virtual environments

* **[Kubernetes OpenStack tutorials](#id-70BestKubernetesTutorials-openstack)** - deploying Kubernetes on an OpenStack, a popular private cloud platform

* **[Clustering and federation tutorials](#id-70BestKubernetesTutorials-clustering)** - Kubernetes clusters in-depth

* **[CI/CD tutorials](#id-70BestKubernetesTutorials-ci/cd)** - using Kubernetes to set up CI/CD and continuous deployment pipelines

* **[Networking tutorials](#id-70BestKubernetesTutorials-network)** - networking concepts, load balancing, security and more

* **[Helm tutorials](#id-70BestKubernetesTutorials-helm)** - using the [Helm](/display/containers/Kubernetes+Helm+101) package manager to create charts and deploy them easily on a Kubernetes cluster

* **[Kubernetes with popular languages and frameworks](#id-70BestKubernetesTutorials-frameworks)** - Node.js, Python/Django, Ruby/Rails, Spring and Neo4j

* **[Monitoring tutorials](#id-70BestKubernetesTutorials-monitoring)** - monitoring Kubernetes deployment using Prometheus and other tools.

* **[Kubernetes Windows and Mac tutorials](#id-70BestKubernetesTutorials-windows)** - running Kubernetes on popular operating systems

* **[Kubernetes in other environments](#id-70BestKubernetesTutorials-other)** - including MongoDB, LAMP and SAP HANA








