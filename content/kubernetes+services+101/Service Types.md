---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 5  # Order that this section will appear.
title: "Service Types"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
The default and simplest service type is `ClusterIP` . It exposes the service’s ClusterIP address internally to the Kubernetes cluster. Other types allow different access policies to the service and include:

* **`NodePort`** - exposes the service on the specified port number, on all nodes in the Kubernetes cluster. Meaning that an incoming request to a node’s IP on the specified port will get routed to the service’s ClusterIP .

* **`LoadBalancer`** - service is exposed like in NodePort but creates a load balancer in the cloud where Kubernetes is running (if supported by the cloud provider) that receives external requests to the service. It then distributes them among the cluster nodes using NodePort. To specify this type add this line to the spec:

`type: LoadBalancer`

* **`ExternalName`** - returns an alias to an external component residing outside the Kubernetes cluster. An incoming request for the service gets routed by Kubernetes DNS to the external domain specified. For example, to redirect traffic sent to my-service to [my.database.example.com](http://my.database.example.com) :

```
kind: Service
apiVersion: v1
metadata:
  name: my-service
  namespace: default
spec:
  type: ExternalName
  externalName: my.database.example.com
```

	
**For further reading, see Kubernetes Documentation:** {{< read-more "Publishing services - service types" "https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services---service-types" "_target"  >}}	
		
		