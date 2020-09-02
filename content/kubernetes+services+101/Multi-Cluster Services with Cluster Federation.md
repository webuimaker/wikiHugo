---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 8  # Order that this section will appear.
title: "Multi-Cluster Services with Cluster Federation"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
Kubernetes Cluster Federation allows a (federated) service to run on multiple Kubernetes clusters simultaneously. The clusters can be spread across different cloud providers, availability zones and even private clouds, as long as the cluster’s API endpoint and credentials are registered with the Federation API server.

A new federated service can be created by calling the Federation API in the same manner as a cluster-specific kube-apiserver would be called for a (non-federated) service (as described in this article up to now). Federation means that the service will be sharded across all the Kubernetes clusters that are part of the federation.

A pod can access a federated service in a similar fashion to a regular service, by adding the federation name. For example calling `my-service.my-namespace.my-federation` gets automatically resolved by Kubernetes DNS server to the (geographically) nearest cluster where the service is running (under normal circumstances this would be service shard in the same cluster where the pod resides).

The health of the service in each cluster is automatically monitored and a set of DNS records is kept up-to-date accordingly. Such records are set up in an hierarchical way. For example, a request sent to the top-level record:

`my-service.mynamespace.my-federation.svc.example.com`

could get forwarded to any (healthy) service endpoint on any of the federated clusters (on any zone, region or provider). However, a request sent to

`my-service.my-namespace.my-federation.svc.europe-west1-d.example.com`

will get forwarded to an endpoint in a cluster inside availability zone europe-west1-d.

Should there be no healthy service shard running in that zone, the request will get forwarded to a cluster on another availability zone in the europe-west1 region, Should that still fail to reach a healthy service, then the request would get forwarded to the top-level:

`my-service.mynamespace.my-federation.svc.example.com`

and possibly get handled by a service shard in a different region or even a different cloud provider.

Federation provides high availability of services, availability zone fault tolerance and built-in service discovery across multiple zones, regions, providers and on-premise clusters.



	
**For further reading, see Kubernetes Documentation:** {{< read-more "Cross-cluster Service Discovery using Federated Services" "https://kubernetes.io/docs/home/" "_target"  >}}	
		
		