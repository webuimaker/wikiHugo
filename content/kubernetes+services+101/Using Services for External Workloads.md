---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 4  # Order that this section will appear.
title: "Using Services for External Workloads"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
A service can apply to an external workload as well, allowing to use the same abstraction to connect to a backend or database running outside Kubernetes, for example. Pods can then connect to this service and without knowing about specific endpoints for workloads outside of Kubernetes.

In order to do so the service should be defined as in previous section but without the label selector. After the service is created, the endpoints for the external workload need to be specified. For example:

```
kind: Endpoints
apiVersion: v1
metadata:
 name: my-service
subsets:
 - addresses:
- ip: 62.82.24.195
 ports:
 - port: 9376
```
 
All incoming traffic to `my-service` will get routed straight through to endpoint `62.82.24.195:9376`.



**For further reading, see Kubernetes Documentation:** {{< read-more "Services without selectors" "https://kubernetes.io/docs/concepts/services-networking/service/#services-without-selectors" "_target"  >}}	