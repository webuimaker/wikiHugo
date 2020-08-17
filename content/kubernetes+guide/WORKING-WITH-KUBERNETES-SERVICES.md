---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 5  # Order that this section will appear.
title: "5.WORKING WITH KUBERNETES SERVICES"
titleColor: 
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---

For Kubernetes, a service is an abstraction that represents a set of logical pods where an application or component is running, as well as embedding an access policy to those pods. Actual pods are ephemeral, Kubernetes guarantees the availability of pods and replicas specified but not the liveliness of each individual pod. This means that other pods that need to communicate with this application or component cannot rely on the underlying individual pod’s IP addresses.

A service gets allocated a virtual IP address as well (called a **clusterIP** in Kubernetes), and lives until explicitly destroyed. Requests to the service get redirected to the appropriate pods, thus the service serves as a stable endpoint used for inter-component or application communication. For Kubernetes-native applications, requests can also be made via an API in Kubernetes’ apiserver which automatically exposes and maintains the actual pods endpoints at any moment.

## Specifying Pods in a Service

A service in Kubernetes can be created via an API request by passing in a service definition such as:

```java
kind: Service
apiVersion: v1
metadata:
  name: my-service
spec:
  selector:
    app: MyApp
  ports:
    - protocol: TCP
      port: 80
      targetPort: 9376
```

## Using Services for External Workloads


A service can apply to an external workload as well, allowing to use the same abstraction to connect to a backend or database running outside Kubernetes, for example. Pods can then connect to this service and without knowing about specific endpoints for workloads outside of Kubernetes.

In order to do so the service should be defined as in previous section but without the label selector. After the service is created, the endpoints for the external workload need to be specified. For example:

```java
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

## Service Discovery

Service discovery in Kubernetes can be achieved via the cluster DNS (recommended) or via environment variables on the nodes.

Kubernetes exports a set of environment variables for each service currently active in the Kubernetes cluster at pod creation time. These variables are exported on the node where the pod gets created, so they become visible to the pod. For example, these variables (and more) would get exported for each of the active services ```payments``` and ```orders``:

```java
PAYMENTS_SERVICE_HOST=10.0.0.11
PAYMENTS_SERVICE_PORT=6379
ORDERS_SERVICE_HOST=10.0.171.239
ORDERS_SERVICE_PORT=6379
```

## Multi-Cluster Services with Cluster Federation

Kubernetes Cluster Federation allows a (federated) service to run on multiple Kubernetes clusters simultaneously. The clusters can be spread across different cloud providers, availability zones and even private clouds, as long as the cluster’s API endpoint and credentials are registered with the Federation API server.

A new federated service can be created by calling the Federation API in the same manner as a cluster-specific kube-apiserver would be called for a (non-federated) service (as described in this article up to now). Federation means that the service will be sharded across all the Kubernetes clusters that are part of the federation.

**Learn more about working with** {{< read-more "Kubernetes Services" "/display/containers/kubernetes+services+101"  >}}
