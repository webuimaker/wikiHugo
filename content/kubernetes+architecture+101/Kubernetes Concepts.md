---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 3  # Order that this section will appear.
title: "Kubernetes Concepts"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---

Making use of Kubernetes requires understanding the different abstractions it uses to represent the state of the system, such as services, pods, volumes, namespaces, and deployments.

*   [**Pod**](https://kubernetes.io/docs/concepts/workloads/pods/pod-overview/) -generally refers to one or more containers that should be controlled as a single application. A pod encapsulates application containers, storage resources, a unique network ID and other configuration on how to run the containers.
*   **[Service](https://kubernetes.io/docs/concepts/services-networking/service/)** - pods are volatile, that is Kubernetes does not guarantee a given physical pod will be kept alive (for instance, the replication controller might kill and start a new set of pods). Instead, a service represents a logical set of pods and acts as a gateway, allowing (client) pods to send requests to the service without needing to keep track of which physical pods actually make up the service.
*   **[Volume](https://kubernetes.io/docs/concepts/storage/volumes/)** -similar to a container volume in Docker, but a Kubernetes volume applies to a whole pod and is mounted on all containers in the pod. Kubernetes guarantees data is preserved across container restarts. The volume will be removed only when the pod gets destroyed. Also, a pod can have multiple volumes (possibly of different types) associated.
*   **[Namespace](https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/)** -a virtual cluster (a single physical cluster can run multiple virtual ones) intended for environments with many users spread across multiple teams or projects, for isolation of concerns. Resources inside a namespace must be unique and cannot access resources in a different namespace. Also, a namespace can be allocated a [resource quota](https://kubernetes.io/docs/concepts/policy/resource-quotas/) to avoid consuming more than its share of the physical cluster’s overall resources.
*   **[Deployment](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)** -describes the desired state of a pod or a replica set, in a yaml file. The deployment controller then gradually updates the environment (for example, creating or deleting replicas) until the current state matches the desired state specified in the deployment file. For example, if the yaml file defines 2 replicas for a pod but only one is currently running, an extra one will get created. Note that replicas managed via a deployment should not be manipulated directly, only via new deployments.

**For further reading, see Kubernetes Documentation:** {{< read-more "Kubernetes Concepts" "https://kubernetes.io/docs/concepts/" "_target"  >}}








