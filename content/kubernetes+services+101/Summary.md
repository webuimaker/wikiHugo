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
Services are an abstraction that allows the underlying pods to change (some get deleted, some get created) without the service clients needing to keep track of which pods are available at any point. This is done via a clusterIP address for the service. To expose the service to the outside world, the service must be defined as type `NodePort` or `LoadBalancer` . It’s also possible to redirect service requests to an external resource by means of an `ExternalName` type of service. This provides support for inter-operability and migration scenarios. A federated service is essentially a regular service replicated across multiple Kubernetes clusters, which might live in different availability zones, cloud providers or even on-premise, supporting high availability and availability zone fault tolerance.  