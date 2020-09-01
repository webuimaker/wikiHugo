---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 4  # Order that this section will appear.
title: "How Pods Communicate with Each Other"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---

Because each pod has a unique IP in a flat address space inside the Kubernetes cluster, direct pod-to-pod communication is possible without requiring any kind of proxy or address translation. This also allows using standard ports for most applications as there is no need to route traffic from a host port to a container port, as in Docker. Note that because all containers in a pod share the same IP address, container-private ports are not possible (containers can access each other’s ports via `localhost:<port>` ) and port conflicts are possible. However, the typical use case for a pod is to run a single application service (in a similar fashion to a VM), in which case port conflicts are a rare situation.

**For further reading, see community documentation:** {{< read-more "Networking"  "https://github.com/kubernetes/community/blob/master/contributors/design-proposals/network/networking.md" "_blank"  >}}

