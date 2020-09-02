---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 9  # Order that this section will appear.
title: "Common operations with kubectl"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---

The kubectl c ommand line makes it easier to run some common operations with Kubernetes services:

* <strong>Create a service -</strong> It’s possible to specify that all deployed pods in a given deployment are part of a new service. For example this command will create service  ```my-nginx```  which targets TCP port 80 on any pod with the `run: my-nginx` metadata label:


`$ kubectl expose deployment/my-nginx`

* <strong>Describe a service -</strong> This is useful to check that the service was created as expected or to find out its <strong>ClusterIP</strong> or the endpoints of the pods currently part of the service. To describe service `my-nginx`:


`$ kubectl describe svc my-nginx`

* <strong>List all services - </strong>For a full list of services running in the cluster, run `kubectl get services`.

* <strong>Check if Kubernetes DNS service is running :</strong> The DNS service must be up and running for service discovery via name resolution to work. To check if it’s running in a cluster run:

`$ kubectl get services kube-dns --namespace=kube-system`

* <strong>Remove a service - </strong> `kubectl delete` is the command for deleting Kubernetes resources. For example, to remove service `my-nginx` run:

`$ kubectl delete svc my-nginx`






**For further reading, see Kubernetes Documentation:** {{< read-more "kubectl" "https://docs.helm.sh/helm/#helm-repo" "_target"  >}}