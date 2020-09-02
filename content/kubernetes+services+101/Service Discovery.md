---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 6  # Order that this section will appear.
title: "Service Discovery"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
Service discovery in Kubernetes can be achieved via the cluster DNS (recommended) or via environment variables on the nodes.

The DNS server watches the Kubernetes API for new services and creates a set of DNS records for each. Pods can then access services via standard DNS name resolution. If namespaces are being used in the cluster, then pods outside need to qualify the namespace of the service, for example by calling `my-service.my-namespac`e instead of just `my-service` .

Environment variables are less reliable as a pod might fail to reach a service that was created after the pod. Kubernetes exports a set of environment variables for each service currently active in the Kubernetes cluster at pod creation time. These variables are exported on the node where the pod gets created, so they become visible to the pod. For example, these variables (and more) would get exported for each of the active services `payments` and `orders`:

```
PAYMENTS_SERVICE_HOST=10.0.0.11
PAYMENTS_SERVICE_PORT=6379
ORDERS_SERVICE_HOST=10.0.171.239
ORDERS_SERVICE_PORT=6379
```



But if the `orders` service did not exist yet at pod creation time, then `orders` would not be visible to the pod through environment variables.


**For further reading, see Kubernetes Documentation:** {{< read-more "Discovering services" "https://kubernetes.io/docs/concepts/services-networking/service/#discovering-services" "_target"  >}}	
	