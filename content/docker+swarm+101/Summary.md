---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 10  # Order that this section will appear.
title: "Summary"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---

Kubernetes provides a networking model but the specific implementation is done by a third party tool. By default, the model provides full communication inside the cluster (each pod gets its own IP address and can communicate with any other pod or service) and full isolation to the outside world. By specifying ingress rules, incoming outside traffic can be routed to services running in the cluster. Also, network policies specifications allow defining both ingress and egress rules for a set of pods (tagged with a given label) within a namespace. Such rules are defined based, for example, on IP address, namespace or pod labels.

