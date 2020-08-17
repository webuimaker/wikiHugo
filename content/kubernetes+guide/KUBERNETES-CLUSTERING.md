---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 3  # Order that this section will appear.
title: "4.KUBERNETES CLUSTERING"
titleColor: 
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---

A Kubernetes cluster is made of a master node and a set of worker nodes. In a production environment these run in a distributed setup on multiple nodes. For testing purposes, all the components can run on the same node (physical or virtual) by using minikube. Kubernetes has six main components that form a functioning cluster: API server, Scheduler, Controller manager, kubelet, kube-proxy, etcd.

**See our compilation of resources about** {{< read-more "Kubernetes Cluster Administration" "/display/containers/kubernetes+cluster"  >}}

## Cluster Policies

For enterprise production deployments of Kubernetes clusters, enforcing cluster-wide policies to restrict what a container is allowed to do is important. Learn about Kubernetes Cluster Policies such as Pod Security Policies, Network Policies and Resource Quotas.


**See our compilation of resources about** {{< read-more "Kubernetes Cluster Policies" "/display/containers/kubernetes+cluster+policies"  >}}

## Kubernetes Federation

Kubernetes Federation lets you manage deployments and services across all Kubernetes clusters located in different regions. Learn how to set up a Kubernetes Cluster Federation, including tutorials and examples.

**See our compilation of resources about** {{< read-more "Kubernetes Federation" "/display/containers/kubernetes+federation"  >}}

## Kubernetes High Availability Clusters

Kubernetes clusters enable a higher level of abstraction, enabling you to deploy and manage a group of containers that comprises a micro-service. Learn about high availability cluster components and how to setup a high availability Kubernetes cluster. 

**See our compilation of resources about** {{< read-more "Kubernetes High Availability Clusters" "/display/containers/kubernetes+high+availability+clusters"  >}}


## Logging in a Cluster


Application and system logs can help you understand what is happening inside a Kubernetes cluster. Logs are particularly useful for debugging problems and monitoring cluster activity. Kubernetes  provides two logging end-points for applications and cluster logs: Stackdriver Logging for use with Google Cloud Platform and [Elasticsearch](/display/containers/Using+Docker+with+ElasticSearch). Learn about Kubernetes logging architecture including tutorials and examples.

## Kubernetes Proxies

There are several different proxies you may encounter when using Kubernetes: kubectl, apiserver proxy, kube-proxy, a proxy/load-balancer in front of apiserver and a cloud load balancer on external services - the first two types being the most important for Kubernetes users. The cluster admin will ensure that the latter types are setup correctly.

**See our compilation of resources about** {{< read-more "Kubernetes Proxies" "/display/containers/kubernetes+proxies"  >}}

## Kubernetes in a Serverless Computing Model

With serverless computing, you just upload the code somewhere, and it runs whenever you invoke it. Simply put, serverless computing frees you from the complexities of configuring and maintaining Kubernetes clusters. Learn how to build a Serverless Kubernetes cluster.

**See our compilation of resources about** {{< read-more "Kubernetes Serverless" "/display/containers/kubernetes+serverless"  >}}




