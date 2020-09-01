---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 8  # Order that this section will appear.
title: "Network Policies"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---

By default pods can accept traffic from any pod in the cluster. Network policies can restrict how groups of pods are allowed to communicate between them and other network endpoints. A network policy specification uses labels to select pods and define a set of rules which govern what traffic is allowed to and from those pods. For example:

```
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: my-network-policy
  namespace: default
spec:
  podSelector:
    matchLabels:
      role: db
  policyTypes:
  - Ingress
  - Egress
  ingress:
  - from:
    - ipBlock:
        cidr: 172.17.0.0/16
        except:
        - 172.17.1.0/24
    - namespaceSelector:
        matchLabels:
          project: my-project
    - podSelector:
        matchLabels:
          role: frontend
    ports:
    - protocol: TCP
      port: 6379
  egress:
  - to:
    - ipBlock:
        cidr: 10.0.0.0/24
    ports:
    - protocol: TCP
      port: 5978
```

`podSelector` specifies the group of pods on which this network policy should be applied. An empty `podSelector` would select all pods in the namespace. In this example only pods labelled `role: db` in namespace `default` are subject to this policy, which defines both `Ingress` and `Egress` rules.

The `Ingress` rules in this example specify that affected pods can only receive `TCP` traffic on port `6379` if originating from any of these sources:

- IP addresses in CIDR `172.17.0.0/16` but not in CIDR `172.17.1.0/24`
- any pod in the namespace `my-project`
- any pod in the namespace `default` with label `role: frontend`

The `Egress` rules in this example specify that affected pods can only send `TCP` traffic to port `5978` of IP addresses in CIDR `10.0.0.0/24` .

Besides whitelisting traffic sources/targets as in the above example, it is also possible to set default behaviors all incoming or outcoming traffic. For example to deny all incoming traffic to all pods in `default` namespace:

```
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: deny-all-ingress
  namespace: default
spec:
  podSelector: {}
  policyTypes:
  - Ingress
```

And to allow all outgoing traffic from pods in `default` namespace:

```
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: allow-all-egress
  namespace: default
spec:
  podSelector: {}
  egress:
  - {}

```

Note that the network solution in use must support network policies for them to actually take effect. See [Kubernetes Networking Model Implementations](#KubernetesNetworking101-KubernetesNetworkingModelImplementations).

**For further reading, see Kubernetes documentation:** {{< read-more "Network Policies" "https://kubernetes.io/docs/concepts/services-networking/network-policies/" >}}

