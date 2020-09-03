---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 1  # Order that this section will appear.
title: "Key Components of Kubernetes"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"

---


To understand the Kubernetes approach to deployment you need to know the various components that work together.

## Pod
A [pod](https://www.aquasec.com/wiki/display/containers/Kubernetes+Pods) is a group of containers that share common resources like networking and storage and are located on the same node.

## ReplicaSet
A [ReplicaSet](https://kubernetes.io/docs/concepts/workloads/controllers/replicaset/) ensures that all pods have a required number of replicas running at any given time.

## DaemonSet
A [DaemonSet](https://www.aquasec.com/wiki/display/containers/Kubernetes+DaemonSets) ensures that all active nodes are running at least one pod. It dynamically allocates pods on nodes as they are created and removed.

## Deployment
In Kubernetes, a [deployment](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) is a feature that manages pods and ReplicaSets. In other words, as you trigger a release the Deployment controller updates the pods and ReplicaSets by making changes to them or replacing them with newly updated pods and ReplicaSets.

## Helm
[Helm](https://github.com/kubernetes/helm) is growing in popularity as a package manager for Kubernetes. It helps manage charts, which are packages of pre-configured Kubernetes resources. Helm can find and install popular software packaged as Kubernetes charts, share applications as Kubernetes charts, create reproducible builds, manage Kubernetes manifest files and releases used for packages.

DockerHub can also automatically scan images in private repositories for vulnerabilities, producing a report detailing vulnerabilities found in each image layer, by severity (critical, major or minor).

Note that multiple private repos, parallel builds and image security scanning are only available with paid subscriptions.





