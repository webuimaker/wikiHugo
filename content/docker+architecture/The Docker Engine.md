---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 2  # Order that this section will appear.
title: "The Docker Engine"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---

First, let us look take a look at Docker Engine and its components so we have a basic idea of how the system works. Docker Engine allows you to develop, assemble, ship, and run applications using the following components:

1. <strong>Docker Daemon:</strong> A persistent background process that manages Docker images, containers, networks, and storage volumes. The Docker daemon constantly listens for Docker API requests and processes them.

2. <strong>Docker Engine REST API:</strong> An API used by applications to interact with the Docker daemon; it can be accessed by an HTTP client.

3.  <strong>Docker CLI:</strong> A command line interface client for interacting with the Docker daemon. It greatly simplifies how you manage container instances and is one of the key reasons why developers love using Docker.



![Docker Engine](/images/Docker_Engine.png)


Docker Engine




Now that we see how the different components of the Docker Engine are used, let us dive a little deeper into the architecture.




<strong>Implementation</strong>

Docker is available for implementation across a wide range of platforms:

* Desktop: [Mac](/display/containers/Docker+on+Mac) OS, Windows 10.

* Server: Various Linux distributions and Windows Server 2016.

* [Cloud](/display/containers/Docker+in+the+Cloud): Amazon Web Services, Google Compute Platform, Microsoft Azure, IBM Cloud, and more.