---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 7  # Order that this section will appear.
title: "DNS for Services and Pods"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---


Kubernetes provides its own DNS service to resolve domain names inside the cluster in order for pods to communicate with each other. This is implemented by deploying a regular Kubernetes service which does name resolution inside the cluster, and configuring individual containers to contact the DNS service to resolve domain names. Note that this “internal DNS” is compatible and expected to run along with the cloud provider’s DNS service.

Every service gets assigned a DNS name which resolves to the cluster IP of the service. The naming convention includes the service name and its namespace. For example:
`my-service.my-namespace.svc.cluster.local`

A pod inside the same namespace as the service does not need to fully qualify its name, for example a pod in my-namespace could lookup this service with a DNS query for my-service , while a pod outside my-namespace would have to query for `my-service.my-namespace` .

For headless services (without a cluster IP), the DNS name resolves to the set of IPs of the pods which are part of the service. The caller can then use the set of IPs as it sees fit (for example round-robin).

By default pods get assigned a DNS name which includes the pod’s IP address and namespace. In order to assign a more meaningful DNS name, the pod’s specification can specify a hostname and subdomain:

```
apiVersion: v1
kind: Pod
metadata:
  name: busybox
  labels:
    name: busybox
spec:
  hostname: busybox
  subdomain: my-subdomain
  containers:
  - image: busybox
    command:
      - sleep
      - "3600"
    name: busybox
```

In the above example the pod’s DNS name would be:

`busybox.my-subdomain.svc.cluster.local`

and resolve to the pod’s IP address.

Since Kubernetes 1.9, pods DNS settings can be customized in their specification. For example in this spec:

```
apiVersion: v1
kind: Pod
metadata:
  namespace: my-namespace
  name: my-pod-dns
spec:
  containers:
    - name: my-nginx
      image: nginx
  dnsPolicy: "None"
  dnsConfig:
    nameservers:
      - 1.2.3.4
```

Note that `dnsPolicy` set to `None` tells Kubernetes not to apply the default DNS settings, followed by the custom `dnsConfig` settings for this pod. In this example `nameservers` tell Kubernetes to use `1.2.3.4` as the DNS server address for this pod (a maximum of three servers can be specified in the list).

**For further reading, see Kubernetes documentation:** {{< read-more "DNS for Services and Pods" "https://kubernetes.io/docs/concepts/services-networking/dns-pod-service/" "_blank" >}}



