---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 6  # Order that this section will appear.
title: "Docker Swarm and Kubernetes"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---

Nodes inside a Kubernetes cluster are firewalled from the Internet by default, thus services IP addresses are only targetable within the cluster network. In order to allow incoming traffic from outside the cluster, a service specification can map the service to one or more `externalIPs` (external to the cluster). Requests arriving at an external IP address get routed by the underlying cloud provider to a node in the cluster (usually via a load balancer outside Kubernetes). The node then knows which service is mapped to the external IP and also which pods are part of the service, thus routing the request to an appropriate pod.

To support more complex policies on incoming traffic, Kubernetes provides an Ingress API offering externally-reachable URLs, traffic load balancing, SSL termination, and name based virtual hosting to services. An ingress is a collection of rules that allow inbound connections to reach the cluster service. Note that to actually action ingresses specified via the API, an ingress controller (such as the [NGINX ingress controller](https://github.com/kubernetes/ingress-nginx/blob/master/README.md) ) must be deployed and configured for the cluster. This might be done automatically or not, depending on which Kubernetes cloud provider you are using.

A minimal ingress specification might look like this:

```
apiVersion: extensions/v1beta1
kind: Ingress
metadata:
  name: my-ingress
spec:
  backend:
    serviceName: my-service
    servicePort: 80
```

When processing this specification, the ingress controller would allocate an external IP to satisfy `my-ingress` rules, and forward all requests arriving at that IP to `my-service:80` .

A slightly more complex example using simple load balancing could look like this:

```
apiVersion: extensions/v1beta1
kind: Ingress
metadata:
  name: my-ingress
  annotations:
    ingress.kubernetes.io/rewrite-target: /
spec:
  rules:
  - host: foo.bar.com
    http:
      paths:
      - path: /foo
        backend:
          serviceName: my-service-1
          servicePort: 80
      - path: /bar
        backend:
          serviceName: my-service-2
          servicePort: 80
```

In this case all requests sent to `foo.bar.com/foo` get routed (through node load balancing) to `my-service-1:80` while requests sent to `foo.bar.com/bar` get routed (through node load balancing) to `my-service-2:80`

Note that the load balancing strategy is defined by the ingress controller and applied to all ingresses, thus does not appear in the ingress specification.

**For further reading, see Kubernetes documentation: Ingress** {{< read-more "Ingress" "https://kubernetes.io/docs/concepts/services-networking/ingress/" "_blank" >}}