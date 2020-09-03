---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 2  # Order that this section will appear.
title: "What is Docker?"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---

[Docker](https://www.aquasec.com/wiki/display/containers/Docker+Containers) is an open source project that offers a software development solution known as containers. To understand Docker, you need to know what containers are. According to Docker, a container is ” a lightweight, stand-alone, executable package of a piece of software that includes everything needed to run it.” And since containers are platform-independent, Docker can run across both Windows- and Linux-based platforms. In fact, Docker can also be run within a virtual machine if need be. The main purpose of Docker is that it lets you run [microservice applications](/display/containers/Containers+and+Microservices) in a distributed architecture.

## Docker Architecture

Docker’s architecture is also client-server based. However, it’s a little more complicated than a virtual machine because of the features involved. It consists of four main parts:

![alt](/images/docker.JPG)




Source: Docker

1. <strong>Docker Client:</strong> This is how you interact with your containers. Call it the user interface for Docker.

2. <strong>Docker Objects:</strong> These are your main components of Docker: your containers and images. We mentioned already that containers are the placeholders for your software, and can be read and written to. Container images are read-only, and used to create new containers.

3. <strong>Docker Daemon:</strong> A background process responsible for receiving commands and passing them to the containers via command line.

4. <strong>Docker Registry:</strong> Commonly known as [Docker Hub](/display/containers/Working+With+Docker+Hub), this is where your container images are stored and retrieved.



**For more details, see the official site:** {{< read-more "Docker product discovery" "https://www.docker.com/get-docker" "_target"  >}}	