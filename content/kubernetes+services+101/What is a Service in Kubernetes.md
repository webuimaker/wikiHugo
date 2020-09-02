---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 1  # Order that this section will appear.
title: "What is a Service in Kubernetes"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"

---

For Kubernetes, a [service](/display/containers/Kubernetes+as+a+Service) is an abstraction that represents a set of logical pods where an application or component is running, as well as embedding an access policy to those pods. Actual pods are ephemeral, Kubernetes guarantees the availability of pods and replicas specified but not the liveliness of each individual pod. This means that other pods that need to communicate with this application or component cannot rely on the underlying individual pod’s IP addresses.

A service gets allocated a virtual IP address as well (called a <strong>clusterIP</strong> in Kubernetes), and lives until explicitly destroyed. Requests to the service get redirected to the appropriate pods, thus the service serves as a stable endpoint used for inter-component or application communication. For Kubernetes-native applications, requests can also be made via an API in Kubernetes’ apiserver which automatically exposes and maintains the actual pods endpoints at any moment.

**For further reading, see Kubernetes Documentation:** {{< read-more "Services" "https://kubernetes.io/docs/concepts/services-networking/service/" "_target"  >}}