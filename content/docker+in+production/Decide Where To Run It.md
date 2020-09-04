---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 2  # Order that this section will appear.
title: "Decide Where To Run It"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
When running containers in production, an important decision is about where you’ll host your containers. In today’s cloud-powered world nobody wants to build their own datacenter in-house and manage their own servers. In fact, offloading the management of infrastructure to a vendor is seen as a major benefit. This being the case, you need to make a decision about which vendor you find most aligned with your values and goals for a cloud environment for Docker.

The options are endless. The first ones that come to mind are the CaaS services from the cloud vendors. [AWS ECS](https://aws.amazon.com/ecs/), [Azure AKS](https://azure.microsoft.com/en-us/blog/introducing-azure-container-service-aks-managed-kubernetes-and-azure-container-registry-geo-replication/), and [Google Cloud GKE](https://cloud.google.com/kubernetes-engine/) are capable cloud offerings from the big three IaaS platforms. The good thing is if your other infrastructure is with them, you are already familiar with the user interface, and you already use a bunch of supporting tools for monitoring, security, logging, and more. The cloud vendors are in a race to provide the simplest container experience using Kubernetes. Google Cloud was the first to go all out with Kubernetes, followed by Azure rebranding its container service to AKS, and most recently AWS jumped on the bandwagon with EKS now supporting Kubernetes. With the cloud vendors wanting to handle much of the plumbing running Docker in production in one of their platforms is becoming a very attractive proposition.

You’ll need to watch out for vendor lock-in. Getting locked into one system can be a big bet at a time when container technology is so nascent and no vendor is head and shoulders above the rest. If you commit to one now and find it hard to switch to another platform down the line, that is restrictive. However, tools like Kubernetes and the [HashiCorp](https://www.hashicorp.com/) Suite are making hybrid cloud environments a reality.