---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 3  # Order that this section will appear.
title: "Adopt the Service Mesh"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
When you have tens or hundreds of microservices to manage in production, it’s very important to ensure they can communicate with each other. In legacy applications, communication was simple as it was between different parts of the same service. But with microservices apps, communication is complex as each service needs to talk to multiple other services to perform common tasks.

The service mesh is emerging as the default method for [Docker networking](/display/containers/docker+networking+101) container in production. It’s aptly called a mesh because the various connections between services are so complex, it creates a mesh pattern that may seem chaotic, but actually is necessary for normal functioning of a microservices application.

Tools like [Linkerd](https://linkerd.io/) and [Istio](https://istio.io/) are making great progress in how the service mesh is managed.Linkerd provides a consistent data plane for inter-service communication and Istio acts as the control plane for this mesh.

Additionally, tools like [Project Calico](https://www.projectcalico.org/) are segmenting these networks using a policy-based approach. Rather than having a single peripheral firewall, Calico enables micro-firewalls around each service. This way, even if one service is compromised the other services are still protected by their firewall. At the scale of Docker, this type of container-aware security is essential.