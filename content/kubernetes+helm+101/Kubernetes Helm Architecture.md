---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 3  # Order that this section will appear.
title: "Kubernetes Helm Architecture"
titleColor: " "
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---




Helm consists of two main components:

* <strong>Helm Client - </strong>allows developers to create new charts, manage chart repositories, and interact with the tiller server.

* <strong>Tiller Server - </strong>runs inside the Kubernetes cluster. Interacts with Helm client, and translates chart definitions and configuration to Kubernetes API commands. Tiller combines a chart and its configuration to build a release. Tiller is also responsible for upgrading charts, or uninstalling and deleting them from the Kubernetes cluster.
Kubernetes Helm Architecture

![alt](/images/he;m-architecture.png)

[Image Source](https://www.slideshare.net/alexLM/helm-application-deployment-management-for-kubernetes)

After Helm is installed, the `helm init` command installs the Tiller server to your running Kubernetes cluster. It is then possible to search for charts and install them to the cluster.
