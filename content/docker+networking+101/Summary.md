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
Docker offers a mature networking model. There are three common Docker network types - <strong>bridge networks</strong>, used within a single host, <strong>overlay networks</strong>, for multi-host communication, and <strong>macvlan networks</strong> which are used to connect Docker containers directly to host network interfaces.

In this page we explained how Docker containers discover and communicate with each other and how they communicate with the outside world. We showed how to perform common operations such as inspecting a network, creating a new network and disconnecting a container from a network. Finally, we briefly reviewed how docker networking works in the context of common orchestration platforms - [Docker Swarm](/display/containers/Docker+Swarm+101), [Kubernetes Guide](/display/containers/Kubernetes+Guide) and Apache Mesos. 